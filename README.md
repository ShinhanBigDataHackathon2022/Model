# ShinhanBigdataHackathon2022
ShinhanBigdataHackathon2022 

이 대회는 데이터를 공개할 수 없어 EDA, 이상치 제거 파일은 없습니다.
중요변수 추출, 모델링 코드만 공개합니다. 

1. 분석 주제: '증권성향' 고객을 예측하라. '증권성향'이란, 증권사에서 거래할 확률이 높은 고객 

2. 활용 데이터: 22.6월 신한은행 고객 카드 데이터 

3. 분석 과정 

   1) 변수 조작
   - 남성의 경우 0, 여성의 경우 1로 전처리 
   - 학생 세대 (-24세)=1, 사회초년생(25-34)=2, 소비 주도층이자 학부모 세대(35-44)=3, 장년층 부모 세대(45-54)=4, 중년 및 시니어 세대(55세 이상-)=5로 전처리
   - 결제계좌의 경우 A은행=1, B은행=2, A증권사=3, B증권사=4로 전처리
   - 결제정보에 해당하는 167개의 변수는 16가지 대분류로 통합 
   - 패턴코드에 해당하는 6개 변수는 1을 count한 값으로 변경 
   
   2) 이상치 제거 
   - 고객별로 결제정보의 소비 금액 0~10점까지 점수 부여 
   - 결제정보 대분류별 점수의 평균을 계산
   - 매출 점수가 6점 초과 또는 1점 이하인 고객들을 특이고객으로 간주해 이상치 제거 
   
   3) 중요변수 추출
   -Random forest 알고리즘 기반 중요변수 추출 
   -SHAP Value 사용 
   
   4) 모델 선정: LightGBM 
   -다양한 변수의 명확한 관계 파악의 여러움. 예측 시 고차원 연산에 용이한 모델 선정 
   
   5) 예측 모형 기반 고객 특성 추출 
   - 카드 활동 우수 고객 
   - MZ 세대(20대 ~ 40대 초반)가 높은 비율을 차지 
   - Importance feature 중 연료 평균 소비가 낮음 
   
   6) 예측 고객 활용 방안 제시 
   - 탄소(小) 챌린지: 일상생활에서 신한 카드를 이용하는 고객들의 탄소 배출 비용 절감과 신한금융투자 서비스 이용을 유도하는 챌린지 제안 
