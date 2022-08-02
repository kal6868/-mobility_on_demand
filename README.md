# mobility_on_demand 
* 대중교통이 취약한 경로에 대중교통을 대신할 수 있는 이동수단(On Demand Mobility)를 제공하기 위한 데이터 분석   
# Introduction
![github_smart_1](https://user-images.githubusercontent.com/89456014/179484007-a0f24470-f95a-452b-95cf-43502aa938aa.PNG)
![github_smart_2](https://user-images.githubusercontent.com/89456014/179484010-f71eb77b-883a-47d2-8f9a-77cd3f95e8f0.PNG)
* 카카오 택시, 우버 등 언제든지 필요한 시간대에 호출할 수 있는 교통 수단을 온디맨드 모빌리티(On Demand Mobility) 라고 한다.
* 대중 교통 이용이 혼잡하거나 취약한 경로에 온디맨드 모빌리티(On Demand Mobility) 수요가 있을 것으로 예상
<br/></br>
# How to Analysis
![github_smart_3](https://user-images.githubusercontent.com/89456014/179484014-f09d783d-9250-4c43-8e8d-be976021ff12.PNG)
* 1.Folium을 이용하여 승, 하차가 가장 많이 일어나는 상위 지하철 역을 지도에 표시하여 시각화
* 2.Circurity(실제 대중 교통 이동거리/두 지점의 직선거리)의 차이 비교
* 3.동일 거리를 이동하는데 소요되는 시간의 차이 비교
* 4.환승 여부에 따른 Circularity(실제 대중 교통 이동거리/두 지점의 직선거리)의 차이 비교
# Preprocessing
![github_smart_4](https://user-images.githubusercontent.com/89456014/179484015-8f7ae751-c9dd-4873-824c-a9b3067190d4.PNG)
* 분석 전 이상값들을 제거하여 데이터를 정제
  * 출발지와 도착지가 같은 데이터
  * 직선 거리 차이가 0m인 데이터
  * Circurity가 비 정상적으로 크거나 작은 데이터를 IQR를 사용하여 제거
# 1. 지도에 시각화
![github_smart_5](https://user-images.githubusercontent.com/89456014/179484016-a5b86912-d7d0-4fb9-8666-f67c712fed35.PNG)
![github_smart_6](https://user-images.githubusercontent.com/89456014/179484020-fa540759-aa4d-447c-92e0-29af74bed3e0.PNG)
* 대중교통 이용시간이 가장 많은 시간대에서 승, 하자가 가장 많이 이루어지는 20개의 지하철역을 지도에 표시
  * 출근길 2호선 신도림~사당 구간은 매 역이 승차가 가장 많이 이루어지는 경로에 포함되어 교통 혼잡이 예상
  * 출근길 강남~삼성 구간 또한 매 역이 하차가 가장 많이 이루어지는 경로에 포함되어 교통 혼잡이 예상
# 2. 이동거리 비교
![github_smart_7](https://user-images.githubusercontent.com/89456014/179484026-88374b8f-82fe-4e5a-81f2-0adad439e9f4.PNG)
* 지도에서 파악된 2호선의 실제 출근 시간 지하철 혼잡 여부를 분당 이동거리로 파악
  * T-test를 활용하여 비교시 출근 시간 2호선의 분당 이동거리는 다른 호선과 통계적으로 유의한 차이가 나타나는것으로 산출
  * RankSum를 활용하여 비교시 출근 시간 2호선의 분당 이동거리는 다른 호선과 통계적으로 유의한 차이가 나타나는것으로 산출

# 3. 환승 여부에 따른 Circularity 비교
![github_smart_9](https://user-images.githubusercontent.com/89456014/179484031-63491fed-f2ba-490d-8967-3b81d5ecac0d.PNG)
* 환승 여부에 따른 Circurity의 차이를 비교
  * 환승을 했을 경우의 Circurity 값이 더 높게 나타났고, 이는 통계적(T-test)으로 유의한 차이가 나타남
  * 환승을 했을 경우의 Circurity 값이 더 높게 나타났고, 이는 통계적(Ranksum)으로 유의한 차이가 나타남
  
# 4. 대중교통 환승 시 많이 이용하는 상위 경로
![github_smart_10](https://user-images.githubusercontent.com/89456014/182313548-4ccad2fd-feb7-4610-be99-9b69c09f4acd.PNG)
![github_smart_11](https://user-images.githubusercontent.com/89456014/182313557-f69fdef8-4d73-482f-8de6-760816c6f75c.PNG)
* 환승 시 가장 많이 이용하는 경로 Top5중 상위 4개 경로가 관악구에서 강남구로 이동하는 경로로 파악
  * 해당 경로에 셔틀버스 같은 주기적인 이동 서비스를 제공한다면 수요가 있을 것으로 예상
