## 프로젝트 : 일/주/월 지표 통합 주가 예측 AI 모델링

- 기간 : 2023.08.07 ~ 2023.08.27
- 팀원 : 이승연, 임소연, 임형섭, 곽병찬, 김한호
- 분석 도구 : Python, tensorflow
- 분석 환경 : Linux 서버.

***

### 1. 제출파일
  1) Readme.md : 코드 실행 방법 설명
  2) EDA.ipynb : 기본 raw 데이터로 데이터셋을 구축하기 위한 EDA과정을 담은 파일
  3) 데이터셋.ipynb : 기본 raw 데이터부터 주가 일별 데이터, 주별 데이터, 월별 데이터 생성하는 파일 
  4) 모델링.ipynb : 주가데이터로 LSTM모델을 돌려보는 파일, 성능개선 중
  5) csv. : 일별데이터에 대한 파일

***

### 2. 데이터 획득방법
- 기본적으로 주가 공개 데이터를 사용한다
  - 데이터셋.ipynb 파일을 실행하면, 파이썬 pykrx 라이브러리를 통해서 주가 데이터를 다운로드 받고 raw_data.csv와 day_data, week_data, month_data, all_data를 저장한다.
  - 위의 방법으로 데이터 다운로드하면 시간이 오래걸리기 때문에, 우리는 중간 데이터인 raw_data.csv, day_data.csv를 또한 제출파일에 포함한다.
  - week_data, month_data, all_data는 빠르게 생성이 가능하기에 제출파일에 포함하지 않는다.

***

### 3. requirement -> 필요한 사전 설치 프로그램
  1) python
  2) jupyter notebook 혹은 jupyter lab
  3) 코드 실행에 필요한 파이썬 라이브러리
     - numpy
     - pandas
     - tdqm
     - datetime
     - warning
     - pykrx
     - ta
     - matplotlib
     - seaborn
     - tensorflow
     - keras_tuner
     - sklearn
  (기본적으로 설치되어있는 datetime과 warning을 제외하고 나머지는 설치할 수 있도록 코드를 짜놓음)

***

### 4. 실행방법
  case 1. pykrx라이브러리를 이용하여 전체 데이터를 다운로드 받아서 실행시키는 법(데이터 다운로드 시간이 오래걸림)
  1) 제출한 압축 파일의 압축을 푼다
  2) 작업폴더 안에 code폴더를 생성하여 받은 code파일(*.ipynb)을 code에 넣고 data폴더를 생성한다(csv파일들은 불필요)
  3) jupyter notebook이나 lab을 실행하고,
    - 1_데이터셋.ipynb를 보조지표 가져오기(Markdown) 전까지 실행한 후 2_EDA.ipynb를 실행하여 EDA 결과를 본다음 다시 돌아와 남은 데이터셋.ipynb를 전부 실행시킨다.
    - 3_모델링.ipynb에서 처음부터 실행시킨다.
   
  case 2. 제출한 데이터 파일을 사용하는 경우(데이터 다운로드 시간 절약)
  1) 제출한 압축 파일의 압축을 푼다.
  2) 작업폴더 안에 code폴더를 생성하여 받은 code파일(*.ipynb)을 code에 넣고 data폴더에 받은 데이터 파일(data.csv파일)이 위치한지 확인한다.
  3) jupyter noteboo이나 lab을 실행하고,
    - 바로 2_EDA.ipynb를 실행하여 EDA 결과를 본 다음 다시 돌아와 1_데이터셋.ipynb를 주봉 데이터(Markdown)부터 실행시킨다.
    - 3_모델링.ipynb를 처음부터 실행하여 데이터 저장 후 불러오기까지 실행한 뒤 직접 하이퍼 파라미터 모델 학습 실행 이후를 실행시킨다. (하이퍼 파라미터 탐색부분을 넘기면 된다.) .
