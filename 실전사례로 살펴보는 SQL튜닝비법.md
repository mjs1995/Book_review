# 실전사례로 살펴보는 SQL 튜닝비법
# 실행계획
- 실행계획 : 사용자가 SQL을 실행하여 데이터를 추출하려고 할 때, 옵티마이저가 수립하는 작업 절차 
- SQL이 실행되어 데이터를 처리하고자 할 때, 수립되는 데이터 처리 방법임
- 실행계획이 목적했던 대로 수립되지 않으면, SQL의 퍼포먼스에 문제가 발생함
- EXPLAIN PLAN : 실행계획만을 확인할 수 있음 
  - SQL에 대한 실행계획만을 확인할 수 있음
  - 명령을 사용할 때 데이터를 처리하지 않음
  - ![image](https://user-images.githubusercontent.com/47103479/172156005-be75897a-c425-4197-a445-4f0648c56ce3.png)
  - 데이터 처리를 직접하지 않기 때문에 데이터베이스에 부하x
- SET AUTOTRACE : 실행계획과 I/O 관련 정보를 확인할 수 있음 
  - EXPLAIN PLAN 명령과는 달리 한 번의 명령으로, 여러 개의 SQL에 대한 실행계획을 바로 볼 수 있음
  - 다양하게 옵션을 사용할 수 있어서 여러 가지의 정보를 선택적으로 확인할 수 있음
  - ![image](https://user-images.githubusercontent.com/47103479/172156542-f197b902-fac7-444a-8fea-29332ba1e7dd.png)
  - 명령의 옵션
  - ![image](https://user-images.githubusercontent.com/47103479/172156752-4aad49df-74ea-4938-abd7-21f3adb1d76a.png)
