- 예전에는 주로 EC2 인스턴스의 CPU를 얼마나 사용했는지 자랑했다면 지금은 서버리스 아키텍처를 통해 얼마나 저렴하고 빠르게 동일한 처리를 해내고 있는지 이야기함
- AWS 비용 관리를 컴퓨팅, 스토리지, 네트워크, 애플리케이션, 운영 관점에서 다루고 있음 
- 핀옵스가 무엇인지, 어떤 서비스를 어떻게 운영해야 하며 어떤 부분에서 비용을 좀 더 절감할 수 있는지 등 각 서비스를 비교하고, 그 비결을 간접적으로 독자에게 전달함 
- 저자가 만든 KAOtm이라는 방법론을 바탕으로 지식, 구조, 운영 세 가지를 중점적으로 알아보며, AWS 구성 요소와 요금제를 이해함
- 비즈니스가 클라우드로 전환되면서 보안 위험에 노출되지 않도록 해야 했고 데이터 보호, 컴플라이언스(법, 명령 등의 준수), 규정 등과 관련된 과제를 해결해야 했음 
- 클라우드 컴퓨팅의 비용은 새로운 사용량 기반의 요금제, 새로운 소비 모델, 새로운 운영 방법론, 새로운 추적 및 리포팅 시스템 등과 관련 있음 

# KAO_tm 방법론
- KAO_tm
  - 지식(Knowledge)
    - AWS 서비스 비용 최적화의 시작은 서비스의 구성 요소와 요금제를 이해하는 것
    - 활용 사례에 적용할 수 있는 대체 서비스를 이해하는 것도 중요
  - 구조(Architecture)
    - 결국에는 클라우드 아키텍트가 클라우드 환경을 구성하고 배포하는 방법을 안내함
    - AWS에서 어떤 서비스를 어느 리전에서 사용할 것인지, 보안 네트워크를 어떻게 구성하는지, 각 구성 요소가 다른 구성 요소와 상호 작용하는지 등을 의미함 
  - 운영(Operation)
    - 지속적인 모니터링과 추적, 최적화가 필요함
    - 관련 지식과 구조적 이해가 뒷받침되는 지속적인 운영 작업 없이는 비용 최적화를 이룰 수 없음

# 컴퓨팅 서비스 
- AWS EC2 : 종량제 방식으로 제공되는 아마존의 크기 조정과 확장 및 축소가 가능한 컴퓨팅 서비스 
- AWS 람다 : AWS를 사용하면 기본 인프라를 프로비저닝하거나 운영할 필요 없이 서버리스 모드에서 코드를 실행할 수 있음. 애프릴케이션을 업로드하거나 미리 정의된 서버리스 애플리케이션 리포지토리에서 함수를 선택하고 실행을 트리거할 이벤트를 정의하면 됨. 트리거 이벤트가 발생하면 AWS가 함수 실행을 관리함
- AWS 배치 : 배치 작업을 실행하기 위한 관리형 서비스. 작업을 업로드하고 리소스 요구 사항을 정의하면 됨. AWS가 작업 예약과 실행은 물론 기본 인프라의 프로비저닝 및 운여을 처리함 
- 아마존 EC2    
  - EC2 특성
    - 인스턴스 제품군과 유형
      - 범용, 컴퓨팅 최적화, 메모리 최적화, 스토리지 최적화 및 가속 컴퓨팅
      - 일반적인 용도로 설계된 M형(범용 인스턴스 제품군), 컴퓨팅 집약적인 워크로드 용도로 설계된 C형(컴퓨팅 최적화 인스턴스 제품군), 고성능 그래픽 처리를 위해 GPU 카드로 구동되는 G형(가속 컴퓨팅 인스턴스 제품군) 등이 있음 
  - 아마존 EC2 요금제
    - 사용 기간
      - EC2 온디맨드 인스턴스 요금이라 하며 계정 내에서 실행 중인 인스턴스에 대해서만 요금이 청구됨
    - 동일한 유형 내 인스턴스 크기별 가격
      - 일반적으로 인스턴스 크기가 커질 때마다 (예를 들면 large에서 xlarge로) 프로비저닝된 리소스양(예를 들면 vCPU 수, 메모리양, 스토리지양)이 두 배로 증가함 
    - 동일 유형 내 인스턴스 세대별 가격
    - 인스턴스 유형별 가격 
    - AWS 리전과 로컬 영역
      - 미국 동부 지역이 가장 저렴함. 가격은 유럽과 아시아 태평양, 또는 남아메리카 쪽으로 이동할수록 상승함 
    - 테넌시: 공유 호스트와 전용 호스트 그리고 베어 메탈
      - 공유 테넌시에서는 여러 사용자가 동일한 물리 호스트에서 제공하는 컴퓨팅 리소스를 사용할 수 있음 
      - 전용 호스트 및 베어 메탈 인스턴스는 호스트의 모든 리소스가 프로비저닝되며 한 번에 하나의 클라우드 계정에서만 사용됨 
    - CPU 인스턴스 최적화
    - 일래스틱 그래픽
    - 일래스틱 추론
      - 일래스틱 추론을 사용하면 모든 EC2 및 세이지메이커 인스턴스 또는 아마존 ECS 작업에 GPU 기반 과속을 연결하여 딥러닝 추론을 실행할 수 있음 
    - EC2 구매 옵션 
      - 온디맨드 인스턴스 : 온디맨드는 EC2 인스턴스를 구매하는 기본 방법
      - 예약 인스턴스(RI) : 12개월 또는 36개월 동안 예약된 용량에 대한 비용을 지불하는 대신 EC2 온디맨드 가격에서 최대 72% 할인된 가격으로 제공되는 EC2 인스턴스
      - 세이빙 플랜 : 12개월 또는 36개월 동안 약정된 지출(시간당 달러)을 대가로 EC2 온디맨드 가격에서 최대 72% 할인을 제공함
      - 온디맨드 용량 예약 : EC2 인스턴스의 용량을 일정 기간 동안 특정 가용 영역에서 예약할 수 있음 
      - 스팟 인스턴스 : 아마존 EC2 스팟 인스턴스를 사용하면 EC2 온디맨드 가격에 비해 최대 90% 할인된 가격으로 아마존의 여유 EC2 용량을 활용할 수 있음 
- 아마존 EC2 구매 옵션 
  - 예약 인스턴스
    - 예약 조건 
      - 리전 또는 가용 영역
      - 인스턴스 유형
      - 인스턴스 플랫폼
      - 인스턴스 테넌시
      - 예약 기간
      - 적용 범위
      - 결제 옵션
    - 예약 인스턴스 마켓플레이스
      - 마켓플레이스를 활용하여 약정 기간이 12개월 미만인 예약을 구매할 수 있음. 경우에 따라 예약 인스턴스의 비용보다 훨씬 저렴한 가격으로 제공되는 예약도 찾을 수 있음 
    - 장기 약정의 위험성을 완화할 수 있는 2가지 방법
      - 컨버터블 예약으로, 요구 사항이나 워크로드가 변경될 경우 약정을 수정할 수 있음 
      - 예약 인스턴스 마켓 플레이스를 통해 불필요한 예약 인스턴스를 판매할 수 있음
  - 세이빙 플랜
    - 유형
      - EC2 인스턴스 세이빙 플랜
      - 컴퓨팅 세이빙 플랜 
    - 다른 유형의 세이빙 플랜
      - 세이빙 플랜은 데이터 과학자와 개발자가 고품질 머신러닝 모델을 준비, 구축, 교육 및 배포하는 데 사용하는 서비스인 아마존 세이지메이커에도 사용할 수 있음
      - 세이지메이커 세이빙플랜은 12개월 또는 36개월의 지출 약정(시간당 달러 지출)을 대가로 세이지메이커 인스턴스 사용량을 최대 64%까지 할인해 줌 
    - 세이빙 플랜은 EC2, 파게이트, 람다 비용을 최대 72%까지 절감할 수 있는 좋은 방법을 제공함 
  - 스팟 인스턴스 
    - EC2 플릿
      - AWS에서 제공하는 메커니즘으로, 리전 내에서 원하는 총 용량을 사용하여 온디맨드와 스팟 인스턴스 플릿을 시작하는 프로세스를 간소화함 
    - 인스턴스 중단을 완하하기 위해 구축된 플랫폼 아키텍처, 오토 스케일링 그룹, EC2 플릿, AWS 스팟 인스턴스 어드바이저, 스팟 배치 점수 및 스팟 중단 주입을 조합하여 사용하면 거의 모든 워크로드에서 스팟 인스턴스를 사용할 수 있음 
    - 개발 테스트, 프로덕션 환경까지 포함하고 스팟 인스턴스가 컨테이너 (EKS 및 ECS), EMR, 카산드라, 오픈서치, 하둡, 배치 및 CI/CD를 실행하는 워크로드를 지원함
    - 주요 예외는 데이터베이스와 스테이트풀 애플리케이션. 이러한 애플리케이션의 특성으로 중단 처리가 더 어려워짐
- EC2 오토 스케일링
  - 주어진 순간에 워크로드를 지원하는 데 필요한 컴퓨팅 파워를 프로비저닝하는 동시에 초과 프로비저닝된 인프라의 과도한 지출과 비효율성을 줄이거나 제거할 수 있음 
  - 트래픽이 증가하면 더 많은 인스턴스가 프로비저닝되고 트래픽이 감소하면 인스턴스가 종료되어 사용량이 줄게 되며 사용하지 않는 인프라에 대한 요금이 부과되지 않음 
  - 스케일링 정책
    - 정책은 동적 스케일링에 사용됨. CPU, 메모리, 네트워크 사용률, SQS 대기열 크기, 세션수와 같은 메트릭을 기반으로 스케일링을 트리거하도록 정책을 설정할 수 있음 
  - 오토스케일링 그룹을 사용한 로드 밸런싱
    - 로드 밸런서는 오토 스케일링 그룹 내의 인스턴스 간의 트래픽 분산을 처리함.
    - 일래스틱 로드 밸런싱을 사용하여 오토 스케일링을 사용하도록 설정하면 오토 스케일링에 의해 시작된 인스턴스가 로드 밸런서에 자동으로 등록되고 트래픽이 해당 인스턴스로 라우팅됨
    - 오토 스케일링에 의해 종료된 인스턴스는 로드 밸런서에서 자동으로 등록이 취소되어 트래픽 분산이 중지됨
- 오토 스케일링 요금제
  - 오토 스케일링 그룹을 설정해도 비용이 들지 않음
  - 오토 스케일링 정의에 따라 구동되어 실행 중인 EC2 인스턴스에 대해서만 지불하면 됨. 오토 스케일링이 인스턴스 수를 줄이면 비용 지불이 중지됨
- 오토 스케일링은 주어진 순간에 부하를 지원하는 데 필요한 EC2 인스턴스 수와 컴퓨팅 리소스 용량을 확보하고 초과 프로비저닝된 용량의 낭비를 제거함
- 오토 스케일링은 워크로드 요구 사항에 맞게 인스턴스 용량을 유지 관리하고 가용 영역에 인스턴스를 배포하므로 애플리케이션 복원력과 성능이 향상됨
- 오토 스케일링을 활용하면 효율성, 비용 효율성, 애플리케이션 가용성이 향상됨
- EC2 스케줄링
  - 효율성과 종량제는 클라우드 인프라 채택의 주요 추진 요인 중 하나
  - 수요에 따라 리소스를 확장하거나 축소할 수 있으므로 기존 데이터 센터 운영에 비해 운영 효율성이 향상될 것 
  - AWS 인스턴스 스케줄러
    - 스케줄 정의에 따라 EC2와 RDS 인스턴스를 자동으로 켜고 끄는 스케줄을 설정하여 수동 작업이나 중지/시작 스크립팅에 대한 많은 투자를 줄일 수 있음 
    - 스케줄 : 리소스를 특정 스케줄과 연결하려면 태그 키 (스케줄)와 태그 값(스케줄 이름)을 적용해야 함 
  - 인스턴스 스케줄러 요금제
    - 각 스케줄마다 AWS 람다 요금으로 매월 5달러가 청구됨
    - 실행 중인 EC2 인스턴스와 무관하며, EC2 인스턴스 비용에 추가로 청구됨 
- 서버리스 컴퓨팅
  - EC2는 코드가 실행되는 인프라 계층을 담당하는 IaaS 모델을 기반으로 함
  - EC2 인스턴스의 프로비저닝, 구성, 운영, 모니터링, 최적화 및 유지 보수를 해야 할 책임이 있음
  - 서버리스 컴퓨팅은 사전 정의된 트리거(이벤트)에 대응하여 서버에서 코드(특정 함수)가 자동으로 실행되는 FaaS(Function as a Service) 모델로 운영됨
  - 서버리스 컴퓨팅의 장점
    - 애플리케이션 비즈니스 로직에 집중할 수 있게 함
    - 클라우드 인프라 관리에 드는 노력과 비용을 절감함 
    - 애플리케이션 실행을 위한 최적의 인스턴스 유형 선택, 인스턴스 프로비저닝 자동화, 로드 밸런싱 설정, 오토 스케일링 구성, 운영 체제 패치, 코드 배포 등을 하지 않아도 됨 
  - AWS 람다
    - AWS 람다를 도입하여 이벤트 트리거 함수 호출 문제를 해결하기 위해 서버리스 기능을 최초로 출시했음 
    - 람다를 사용하면 사용자가 자체 애플리케이션 코드를 배포하거나 AWS 서버리스 애플리케이션 리포지토리에 저장된 미리 정의된 다양한 함수 중에서 선택할 수 있음 
    - 함수 트리거
      - 다양한 이벤트를 기반으로 람다 함수 호출을 트리거할 수 있음 
      - S3 : 객체 생성 및 삭제와 같은 S3 버킷 이벤트
      - 애프리케이션 로드 밸런서 : ALB에 도달하는 HTTP 및 HTTPS 요청은 요청 도메인, 요청 방법(GET, PUT, POST) 또는 URL에 따라 람다 함수로 라우팅될 수 있음
      - API 게이트웨이 : API 게이트웨이를 사용하여 서로 다른 API 호출, 원본 또는 엔드포인트에 따라 람다 함수를 호출함
      - 아마존 푸시 알림 서비스 : 아마존 SNS 토픽에 새 메시지가 게시되면 해당 메시지를 람다 함수의 매개변수로 사용함 
      - 아마존 이메일 서비스 
      - 다이나모 DB
      - 키네시스 데이터 스트림, 키네시스 데이터 파이어호스
