# GBM(Gradient Boosting Machine) 

> 부스팅 알고리즘 중 하나인 GBM 정리



### 부스팅 알고리즘

여러 개의 약한 학습기를 순차적으로 학습-예측하면서 잘못 예측한 데이터에 가중치 부여를 통해 오류를 개선해 나가면서 학습하는 방식

##### AdaBoost(Adaptive boosting)

오류 데이터에 가중치를 부여하면서 부스팅을 수행하는 대표적인 알고리즘

##### GBM(Gradient Boosting Machine)

에이다부스트와 유사하나, 가중치 업데이트를 경사 하강법(Gradient Descent)을 이용해서 수행

- 경사 하강법(Gradient Descent): 반복 수행을 통해 오류를 최소화할 수 있도록 가중치의 업데이트 값을 도출하는 기법
  - `오류값`: 실제값 - 예측값
  - 분류의 실제 결과값을 `y`, 피처를 `x`, 예측함수를 `F(x)`라고 했을 때, 오류식은 `h(x) = y - F(x)`

##### 

### GBM 하이퍼 파라미터

| 파라미터명    | 설명                                                         |
| ------------- | ------------------------------------------------------------ |
| n_estimators  | - weak learner의 개수<br />- weak learner가 순차적으로 오류를 보정하므로 개수가 많을 수록 예측 성능이 일정수준까지는 좋아질 수 있음, default는 100 |
| loss          | - 경사 하강법에서 사용할 비용 함수를 지정,  default는 deviance |
| learning_rate | - GBM이 학습을 진행할 때마다 적용하는 학습률, Weak learner가 순차적으로 오류 값을 보정해나가는 데 적용하는 계수<br />- 0~1사이의 값을 지정, default는 0.1 |
| subsample     | - weak learner가 학습에 사용하는 데이터의 샘플링 비율<br />- default는 1, 전체 학습 데이터를 기반으로 학습한다는 의미 |