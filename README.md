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
# 1. 지도에 시각화
![github_smart_5](https://user-images.githubusercontent.com/89456014/179484016-a5b86912-d7d0-4fb9-8666-f67c712fed35.PNG)
![github_smart_6](https://user-images.githubusercontent.com/89456014/179484020-fa540759-aa4d-447c-92e0-29af74bed3e0.PNG)
# 2. Circularity 비교
![github_smart_7](https://user-images.githubusercontent.com/89456014/179484026-88374b8f-82fe-4e5a-81f2-0adad439e9f4.PNG)
# 3. 이동시간 비교
![github_smart_8](https://user-images.githubusercontent.com/89456014/179484027-9158c267-4856-499d-8a6f-2304a5b2eae0.PNG)
# 4. 환승 여부에 따른 Circularity 비교
![github_smart_9](https://user-images.githubusercontent.com/89456014/179484031-63491fed-f2ba-490d-8967-3b81d5ecac0d.PNG)
![github_smart_10](https://user-images.githubusercontent.com/89456014/179484033-e7b2f745-2a19-4c5f-9c71-284ec0e5e1c2.PNG)
