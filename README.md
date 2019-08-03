# LshoppingMall_data_analysis

롯데 데이터를 이용한 고객 데이터 분석

데이터의 구성은 사용자의 기본 정보, 접속 기록, 접속 후 한 행동(구매, 검색, 클릭 등), 상품 정보입니다. 


## 1. basic EDA
Bais EDA 수행
기본적인 세션(사용자가 접속을 한 경우)별로 단일 변수들(구매, 페이지 조회, 접속 시간, 지역, 등)에 대한 시각화
구매&단일변수들 간의 관계 파악

- 1. 구매와 페이지 조회 시각화
  + 1-1. 세션별 페이지 조회 변수 시각화
  + 1-2. 페이지조회와 구매의 관계 파악

- 2. 구매와 세션 접속시간 시각화
  + 2-1. 세션별 세션 접속시간 변수 시각화
  + 2-2. 세션 접속 시간과 구매의 관계 파악

- 3. 구매와 접속 기기유형 시각화
  + 3-1. 세션별 접속 기기유형 변수 시각화
  + 3-2. 접속 기기유형과 구매의 관계 파악
  + 3-3. 기기 유형에 따른 상품 소비 시각화

- 4. 구매와 접속 지역 시각화
  + 4-1. 세션별 접속 지역 변수 시각화
  + 4-2. 접속 지역과 구매의 관계 파악

- 5. 데스크탑 유저의 특징 시각화
  + 5-1. 페이지 조회
  + 5-2. 접속 시간
  + 5-3. 성별
  + 5-4. 연령
  + 5-5. 검색어
- 6. 구매와 상품군 시각화


## 2. CLV(Customer Life Time Value) Analysis
CLV모델 정의
frequency(빈도)는 고객이 반복 구매 한 횟수를 나타냅니다. 즉, 총 구매 횟수보다 1 적은 값 입니다.
T(생존나이)는 선택된 시간 단위의 고객의 생존일수를 나타냅니다. 이것은 고객의 첫 구매와 연구 기간의 끝 사이의 기간과 동일합니다.
recency(최근 구매 일)은 가장 최근에 구매 한 고객의 T를 나타냅니다.
-> 이는 고객의 첫 구매와 최신 구매 간의 기간과 동일합니다. (따라서 1회만 구매 한 경우 recency 값이 0 입니다)

1. RFM 분석
고객들이 접속한 행동, 구매한 행동의 기반으로 어떤 특성을 갖고 있는지 분석합니다.
2. RFM 분석을 바탕으로 그룹화한 집단을 이용해 분류 문제 수행
1번의 세가지 특징을 바탕으로 클러스터링을 진행하고 나뉜 그룹 번호를 이용해 분류 문제를 수행합니다.


## 3. Cohort Analysis
1. 월별로 고객을 나눠서 집단을 구성한다.
2. 집단들 각각의 이탈율을 파악한다.
