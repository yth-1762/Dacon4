# 데이콘 AI 경진대회4

# 일시
- 2024-02-13 ~ 2024-03-04

# 주제
- 웹 로그 기반 조회수 예측 해커톤

# 목적
- 웹 로그 기반 데이터를 활용하여 조회수를 예측
 

# 데이터
- https://dacon.io/competitions/official/236226/data(데이터 출처)
- 데이터 개수 : 252289개
  
| Column               | Non-Null Count   | Dtype   |
|----------------------|------------------|---------|
| sessionID            | 252289 non-null  | object  |
| userID               | 252289 non-null  | object  |
| TARGET               | 252289 non-null  | float64 |
| browser              | 252289 non-null  | object  |
| OS                   | 252289 non-null  | object  |
| device               | 252289 non-null  | object  |
| new                  | 252289 non-null  | int64   |
| quality              | 252289 non-null  | float64 |
| duration             | 252289 non-null  | float64 |
| bounced              | 252289 non-null  | int64   |
| transaction          | 252289 non-null  | float64 |
| transaction_revenue  | 252289 non-null  | float64 |
| continent            | 252289 non-null  | object  |
| subcontinent         | 252289 non-null  | object  |
| country              | 252289 non-null  | object  |
| traffic_source       | 252289 non-null  | object  |
| traffic_medium       | 252289 non-null  | object  |
| keyword              | 114614 non-null  | object  |
| referral_path        | 91182 non-null   | object  |



  

# 사용언어/ 최종 선정 모델
- python/ lgbm

# 모델 성능 지표
- RMSE

# EDA
- 범주형 변수('browser', 'OS', 'subcontinent', 'country', 'traffic_source','device', 'continent', 'traffic_medium')들을 countplot으로 확인(chrome, windows, america,  google,desktop, organic 등이 가장 많은 것을 확인)
- 범주형 변수별 평균 target(조회수) countplot으로 확인
- 수치형 변수('new', 'quality', 'duration', 'bounced', 'transaction', 'transaction_revenue')들을 countplot으로 확인
- new, bounced의 평균 조회수를 barplot으로 확인(new, bounced의 경우 0일 때가 1일 때보다 더 많음)
- 수치형 변수들의 상관관계 heatmap을 통해 확인(transaction과 transaction_revenue가 0.46, transaction과 quality가 0.48로 그나마 높은 상관관계를 보이는 것을 확인)
- continent별 new와, bounced의 평균 조회수 barplot으로 확인(모든 continent가 new가 0일 때 1일 때보다 평균 조회수가 높음-> 접속 경험이 있는 이용자들은 처음 접속한 이용자들보다 조회수가 높음)
- continent별 quality의 평균 조회수 barplot 확인(america의 경우 quality의 수가 높아질수록 tatget이 높아지는 경향을 보임)
- continent별 transaction의 평균 조회수 barplot 확인(transaction이 높을수록 평균 조회수가 높아지는 경향을 보임)
- device별 new의 평균 조회수 barplot으로 확인(desktop은 new가 0일 때 평균 조회수가 더 높고 mobile과 tablet은 1일 때 더 높음)
- device별 bounced의 평균 조회수 barplot으로 확인(device모두 new가 0일 때 압도적으로 높음)
- device별 transaction의 평균 조회수 barplot으로 확인(device 모두 transaction이 높을수록 평균 조회수가 높음)
- traffic_medium별 new, bounced의 평균 조회수 barplot으로 확인(모든 traffic_medium이 newr가 0일 때 평균 조회수가 높음)
- traffic_medium별 quality,transaction의 평균 조회수 barplot으로 확인(모든 traffic_medium이 quality가 높아질수록 평균 조회수가 높음)


  

# 데이터 전처리
- 

# 모델링
- 

# 느낀점
- 
