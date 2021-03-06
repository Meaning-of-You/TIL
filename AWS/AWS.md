# AWS(Amazon Web Services)

> AWS 정리



### AWS

컴퓨팅, 스토리지, 데이터베이스와 같은 인프라 기술부터 기계 학습 및 인공 지능, 데이터 레이크 및 분석, 사물 인터넷 등의 새로운 기술을 제공하는 클라우드 플랫폼

##### 클라우드 컴퓨팅

IT 리소스를 인터넷을 통해 온디맨드로 제공하고 사용한 만큼만 비용을 지불하는 것



### Well-Architected 프레임워크 5대 원칙

1. 보인
2. 성능 효율성
3. 안정성
4. 운영 우수성
5. 비용 최적화



### 보안

클라우드에서 인프라를 보호하는 방법에 중점

##### 멘탈 모델

**제로 트러스트 모델**은 모든 시스템 수준에 보안 조치를 적용하는 것을 의미

##### 개념

- Identity and Access Management(IAM): 시스템에서 ID 및 액세스를 추적하는 서비스
  - 최소 권한 원칙을 사용하는 것을 의미. 즉, 모든 에이전트에게는 기능을 수행하기 위해 필요한 최소한의 권한이 부여

- 네트워크 보안: 네트워크 및 네트워크에 액세스할 수 있는 리소스의 액세스 및 사용성을 보호하는 시스템, 구성 또는 프로세스가 포함
  - 네트워크의 모든 레이어(가장 외부 레이어만이 아닌)에 보안 제어를 적용하는 심층적 방어 접근법이 포함
- 데이터 암호화: 데이터의 암호를 해독하기 위해 필요한 키가 없는 제삼자가 이해할 수 없는 방식으로 정보를 암호화하는 프로세스
  - 모든 곳에 있는 전송 중 및 저장 중 데이터 모두를 암호화하는 것



### 성능 효율성

클라우드에서 서비스를 효율적이고 확장 가능하도록 실행하는 방법에 중점

##### 멘탈 모델

클라우드에서 서버는 **소**처럼 간주. 서버는 몇 초 내에 자동으로 프로비저닝될 수 있는 상용 리소스

- 프로비저닝이 빠르고 저렴하며 워크로드와 가장 일치하는 서버 유형을 자유롭게 선택
- 모든 서버가 호환되고 빠르게 배포할 수 있으므로, 더 많은 서버를 추가하여 용량을 빠르게 확장

##### 개념

- 셀렉트:  워크로드에 가장 적합한 서비스를 선택할 수 있는 기능
- 확장
  - 수직 확장: 기본 컴퓨팅을 더 큰 규모의 인스턴스 유형으로 업그레이드하는 것이 포함
  - 수평 확장: 기본 인스턴스의 수 증가가 포함



### 안정성

서비스 및 인프라 중단 시 복원할 수 있는 서비스의 구축 방법에 중점

##### 멘탈 모델

**파급 범위**는 시스템 장애 발생 시 지속될 수 있는 최대 영향

- 개별 구성 요소의 파급 범위를 최소화

##### 개념

- 장애 격리: 장애 격리 영역으로 구분되는 중복된 독립 구성 요소를 사용하여 문제의 파급 범위를 제한
- 한도: 과도한 부하로부터 서비스를 보호하기 위해 적용될 수 있는 제약
  - Service Quotas: 리전 및 계정을 기준으로 서비스별 한도



### 운영 우수성

시스템 운영, 향상된 절차 개발 및 통찰력 확보 역량을 지속적으로 향상할 수 있는 방법에 집중

##### 멘탈 모델

**자동화**의 측면에서 생각하는 것이 유용

- 오류가 방지될 뿐만 아니라 내부 프로세스가 지속적으로 향상

##### 개념

- 코드형 인프라스트럭처: 시스템에서 읽을 수 있는 구성 파일을 통해 인프라를 관리하는 프로세스
  - IaC는 인프라를 프로비저닝하기 위한 선언적이고 자동화된 방식을 제공
- 관찰 기능: 시스템의 내부 상태를 측정하는 프로세스
  - 일반적으로 원하는 최종 상태로 최적화하기 위해 수행



### 비용 최적화

비용을 최소화하는 동시에 비즈니스 결과를 달성할 수 있도록 지원

##### 멘탈 모델

자본 지출(CapEx) 대신 **운영 비용(OpEx)**의 측면에서 클라우드 비용을 고려

- 운영 비용은 지속적인 종량 과금제 모델이지만 자본 지출은 일회성 구매 모델

##### 개념

- 사용량에 따라 지불: 사용하는 용량에 대해서만 지불
- 비용 최적화 수명 주기: 시간 경과에 따른 클라우드 비용을 향상하는 연속 프로세스

