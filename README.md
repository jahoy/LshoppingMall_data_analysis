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
고객의 접속과 구매에 초점을 맞춰서 분석을 진행하였고, 나온 결과를 바탕으로 클러스터링을 하여 군집을 만들었습니다. 그런 후에 그 군집을 바탕으로 분류 모델을 진행하였습니다.

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
기간별(월)로 나뉜 고객 집단들이 어떤 행태(유지,이탈)를 보이는지 파악하여 기간별 고객의 특성을 파악하였습니다.

1. 월별로 고객을 나눠서 집단을 구성한다.
2. 집단들 각각의 이탈율을 파악한다.

## 4. Market Basket Analysis (Association rules and trend analysis)
고객들의 일별 트랜드를 파악하고, 상품간의 인과관계 및 상관관계를 파악하여 맞춤 캠페인 및 전략 수행이 가능합니다    

- 일별 트렌드 확인 : 일별로 고객들의 접속기기/도시/상품/성별/나이의 특성이 어떻게 변하는지 파악합니다.
  + 대체로 모바일-데스크탑-태블릿 순이며, 각각의 기기에서도 일별로 시계열적인 흐름이 있습니다.
  + 대체로 서울-경기도-인천 순이며, 일별로 시계열적인 흐름이 있습니다.
  + 대체로 남자보다 여자의 접속이 많습니다.
  + 대체로 연령은 30-40대입니다.

- 장바구니분석    
  + 연관규칙분석이란 어떤 두 아이템 집합이 번번히 발생하는가를 알려주는 일련의 규칙들을 생성하는 알고리즘입니다.
경영학에서 장바구니 분석(Market Basket Analysis)으로 널리 알려져 있는 방법론입니다.
소비자들의 구매이력 데이터를 토대로 “X 아이템을 구매하는 고객들은 Y 아이템 역시 구매할 가능성이 높다”는 식의 결론을 내는 알고리즘입니다.
어떤 상품을 고르면 그 상품을 구매한 사람들이 선택한 다른 상품을 제안하는 컨텐츠 기반 추천의 기본이 되는 방법론입니다.

- 각 상품군에 따른 연관관계 결과    
antecedents/consequents는 선후관계입니다. 즉 건강식품을 구매한 고객은 화장품/뷰티케어를 구매할 확률이 높다 라는 결론을 얻을 수 있습니다.        
    
     
주부 : 가구 - 화장품/뷰티케어,  식기 조리기구 - 남성 의류   
남성 : 건강품 - 화장품/뷰티케어 , 구기,필드스포트 - 스포츠 패션   
    
등등 과 같은 결과가 나왔습니다. 이 결과의 쿠폰이나 이벤트를 진행할 때 묶음 할인 및 1+1같은 두 상품을 사게끔 유발하는 전략이 가능합니다.

## 5. Regression analysis
판매량에 영향을 미치는 변수들을 통계적으로 검증하여 보다 논리적인 전략을 수행할 수 있습니다.      
고객들의 검색횟수, 세션 횟수, 세션 머문시간, 접속 지역, 구매 횟수, 성별, 나이, 접속일, 접속주, 접속한 분기등을 이용하여 구매량을 예측합니다.   
   
결과는 pvalue 기준 나이, 분기, 태블릿 사용자, 성별 등이 유의미하다고 나왔습니다.   


## 6. 집단간 통계 분석 (Hypothesis Test)
통계검정을 통해 집단간의 판매량 차이가 있는지 확인할 수 있다.    
검정에는 가정의 제약 자유로운 비모수 검정을 이용하였습니다.   
집단간의 평균과 분산의 차이를 분석하였습니다.   

+ Device에 따른 구매금액의 차이 검정
+ 성별에 따른 구매금액의 차이 검정
+ 나이(젊은층 - 10대, 20대, 30대)에 따른 구매 금액의 차이 검정
+ 나이(노년층 - 40대, 50대, 60대)에 따른 구매 금액의 차이 검정
+ 지역에 따른 구매 금액의 차이 검정 - 서울과 부산

모든 다섯 종류의 분석에서 평균과 분산이 다른 것을 확인하였습니다.
구매 금액에 있어서 Device 기기,성별,나이,지역에 따라 다른 행동 패턴을 보이며 발생하고 있음을 확인하였습니다.

## 7. Clustering
고객의 다양한 특성을 반영하여 고객들을 세그먼트하고 그들의 특성 차이를 파악합니다.    
고객별 평균 접속시간, 구매금액과 나이, 성별 데이터, 고객별 총 접속횟수, 들어온 모든 지역, 구매한 모든 상품 데이터를 결합하여 클러스터링을 진행합니다.    
