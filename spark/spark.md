# Spark 기초

> 스파크의 개념과 주요 기능 정리



### 스파크

고속 범용 분산 컴퓨팅 플랫폼

- 하둡 맵리듀스보다 약 100배 빠른 속도로 같은 작업 수행
- 파이썬, 자바, 스칼라, R 등의 언어 지원
- 일괄처리 작업이나 데이터 마이닝과 같은 온라인 분석 처리 작업에 적합



### 스파크의 컴포넌트

![http://backtobazics.com/big-data/spark/understanding-apache-spark-architecture/](http://backtobazics.com/wp-content/themes/twentyfourteen/images/spark/spark-architecture-and-ecosystem.png)

##### 스파크 코어

스파크 잡과 다른 스파크 컴포넌트에 필요한 기본 기능 제공

- RDD(Resilient Distributed Dataset): 분산 데이터 컬렉션을 추상화한 객체로, 데이터셋에 적용할 수 있는 연산 및 변환 메서드 제공
- HEFS, ClusterFS, 아마존 S3 등 다양한 파일 시스템에 접근 가능
- 공유 변수와 누적 변수를 사용해 컴퓨팅 노드 간에 정보 공유 가능



##### 스파크 SQL

스파크와 하이브 SQL이 지원하는 SQL을 사용해 대규모 분산 정형 데이터를 다룰 수 있는 기능 제공

- DataFrame과 Dataset에 적용된 연산을 일정 시점에 RDD 연산으로 변환해 일반 스파크 잡으로 실행

- Catalyst라는 쿼리 최적화 프레임워크를 제공
- 외부 시스템과 스파크를 연동할 수 있는 아파치 Thrift서버 제공



##### 스파크 스트리밍

다양한 데이터 소스에서 유입되는 실시간 스트리밍 데이터를 처리하는 프레임 워크

- HDFS, 아파치 카프카(kafka), 아파치 플럼(flume), 트위터, ZeroMQ 지원
- 장애가 발생하면 연산 결과를 자동으로 복구
- 이산 스트림 방식으로 스트리밍 데이터를 표현



##### 스파크 MLlib

머신러닝 알고리즘 라이브러리

- 로지스틱 회귀, 나이브  베이즈 분류, 서포트 벡터 머신, 의사 결정 트리, 랜덤 포레스트, 선형 회귀, K-평균 군집화 등 지원
- RDD 또는 dataframe의 데이터 셋을 변환하는 머신 러닝 모델 구현 가능



##### 스파크 GraphX

그래프 RDD 형태의 그래프 구조를 만들 수 있는 다양한 기능 제공

- 페이지랭크, 연결요소, 최단 경로 탐색, SVD++ 등 알고리즘 구현
- 지라프에 구현된 대규모 그래프 처리 및 메시지 전달 API 프리겔 제공

