# GBM(Gradient Boosting Machine) 

> 부스팅 알고리즘 중 하나인 GBM 정리



### 부스팅 알고리즘

여러 개의 약한 학습기를 순차적으로 학습-예측하면서 잘못 예측한 데이터에 가중치 부여를 통해 오류를 개선해 나가면서 학습하는 방식

##### AdaBoost(Adaptive boosting)

오류 데이터에 가중치를 부여하면서 부스팅을 수행하는 대표적인 알고리즘



### GBM(Gradient Boosting Machine)

에이다부스트와 유사하나, 가중치 업데이트를 경사 하강법(Gradient Descent)을 이용해서 수행

- 경사 하강법(Gradient Descent): 반복 수행을 통해 오류를 최소화할 수 있도록 가중치의 업데이트 값을 도출하는 기법
  - `오류값`: 실제값 - 예측값
  - 분류의 실제 결과값을 `y`, 피처를 `x`, 예측함수를 `F(x)`라고 했을 때, 오류식은 `h(x) = y - F(x)`

##### GBM 하이퍼 파라미터

| 파라미터명    | 설명                                                         |
| ------------- | ------------------------------------------------------------ |
| n_estimators  | - weak learner의 개수<br />- weak learner가 순차적으로 오류를 보정하므로 개수가 많을 수록 예측 성능이 일정수준까지는 좋아질 수 있음, default는 100 |
| loss          | - 경사 하강법에서 사용할 비용 함수를 지정,  default는 deviance |
| learning_rate | - GBM이 학습을 진행할 때마다 적용하는 학습률, Weak learner가 순차적으로 오류 값을 보정해나가는 데 적용하는 계수<br />- 0~1사이의 값을 지정, default는 0.1 |
| subsample     | - weak learner가 학습에 사용하는 데이터의 샘플링 비율<br />- default는 1, 전체 학습 데이터를 기반으로 학습한다는 의미 |



### XGBoost(eXtra Gradient Boost)

GBM 기반이지만, GBM의 단점인 느린 수행 시간 및 과적합 규제 부재 등의 문제를 해결해서 곽광받고 있음

- 장점
  - 뛰어난 예측 성능
  - GBM 대비 빠른 수행 시간: 병렬 수행 및 다양한 기능으로 GBM에 비해 빠른 수행 성능 보장
  - 과적합 규제
  - Tree pruning(나무 가지치기): pruning으로 더 이상 긍정 이득이 없는 분할을 가지치기 해서 분할 수를 줄임
  - 자체 내장된 교차 검증: 반복 수행 시마다 내부적으로 교차검증 수행
  - 결손값 자체 처리

##### XGBoost 하이퍼 파라미터

- 일반 파라미터

| 파라미터명 | 설명                                                         |
| ---------- | ------------------------------------------------------------ |
| booster    | - gbtree(tree based model), gblinear(linear model) 선택, default는 gbtree |
| silent     | - 출력 메시지를 나타내고 싶지 않을 경우 1, default는 0       |
| nuthread   | - CPU의 실행 스레드 개수를 조정, default는 CPU의 전체 스레드 사용 |

- 부스터 파라미터

| 파라미터 명                             | 설명                                                         |
| --------------------------------------- | ------------------------------------------------------------ |
| eta[default=0.3, alias: learning_rate]  | - 부스팅 스텝을 반복적으로 수행할 때 업데이트되는 학습률값   |
| num_boost_rounds                        | - weak learner의 개수                                        |
| min_child_weight[default=1]             | - 트리에서 추가적으로 가지를 나눌지 결정하기 위해 필요한 데이터의 weight 총합<br />- 값이 클 수록 분할을 자제, 과적합 조절을 위해 사용 |
| gamma[default=0, alias: min_split_loss] | - 트리의 리프 노드를 추가적으로 나눌지를 결정할 최소 손실 감소 값<br />- 해당 값보다 큰 손실이 감소된 경우에 리프 노드 분리<br />- 값이 클수록 과적합 감소 |
| max_depth[default=6]                    | - 트리의 최대 깊이를 규정, 0을 지정하면 깊이에 제한이 없음<br />- 보통은 3~10 사이의 값 적용 |
| sub_sampling[default=1]                 | -  weak learner가 학습에 사용하는 데이터의 샘플링 비율<br />- 일반적으로 0.5~1 사이의 값 사용 |
| colsample_bytree[default=1]             | - 트리 생성에 필요한 피처를 임의로 샘플링 하는데 사용<br />- 과적합을 조정하는 데 적용 |
| lambda[default=1, alias: reg_lambda]    | - L2 Regularization 적용 값<br />- 값이 클수록 과적합 감소 효과가 있음 |
| alpha[default=0, alias: reg_alpha]      | - L1 Regularization 적용 값<br />- 값이 클수록 과적합 감소 효과가 있음 |
| scale_pos_weight[default=1]             | - 특정 값으로 치우친 비대칭한 클래스로 구성된 데이터 세트의 균형을 유지하기 위한 파라미터 |

- 학습 태스크 파라미터

| 파라미터명      | 설명                                                         |
| --------------- | ------------------------------------------------------------ |
| objective       | - 최솟값을 가져야할 손실 함수를 정의                         |
| binary:logistic | - 이진 분류일 때 적용                                        |
| multi:softmax   | - 다중 분류일 때 적용<br />- 레이블 클래스의 개수인 num_class 파라미터를 지정해야 함 |
| multi:softprob  | - 다중 분류일 때 적용<br />- 개별 레이블 클래스에 해당되는 예측 확률을 반환 |
| eval_metric     | - 검증에 사용되는 함수를 정의, default는 회귀의 경우 rmse, 분류일 경우 error<br />- 값 유형: rmse(Root Mean Square Error), mae(Mean Absolute Error), logloss(Negative log-likelihood), error(Binary classification error rate), merror(Multiclass classification error rate), mlogloss(Multiclass logloss), auc(Area under the curve) |



### LightGBM

일반 GBM 계열의 트리 분할 방법과 다르게 리프 중심 트리 분할 방식 사용

- 장점
  - 더 빠른 학습과 예측 수행 시간
  - 더 작은 메모리 사용량
  - 카테고리형 피처의 자동 변환과 최적 분할: 원-핫 인코딩 등을 사용하지 않고도 카테고리형 피터를 최적으로 변환하고 이에 따른 노드 분할 수행

- 단점
  - 적은 데이터 세트(10,000건 이하)에 적용할 경우 과적합이 발생하기 쉬움

##### LightGBM 하이퍼 파라미터

| 파라미터 명                   | 설명                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| num_iterations[default=100]   | - 반복하려는 트리의 개수를 지정<br />- 크게 지정할수록 예측 성능이 높아질 수 있으나, 너무 크게 지정하면 오히려 과적합으로 성능이 저하될 수 있음 |
| learning_rate[default=0.1]    | - 0~1사이의 값을 지정하며 부스팅 스텝을 반복적으로 수행할 때 업데이트되는 학습률값 |
| max_depth[default=-1]         | - 트리의 최대 깊이를 규정<br />- 깊이가 상대적으로 더 깊음   |
| min_data_in_leaf[default=20]  | -  최종 결정 클래스인 리프 노드가 되기 위해서 최소한으로 필요한 레코드 수<br />- 큰 값으로 설정하면 트리가 깊어지는 것 방지 |
| num_leaves[default=31]        | - 하나의 트리가 가질 수 있는 최대 리프 개수<br />- 개수를 높이면 정확도가 높아지지만, 트리가 깊어지고 모델의 복잡도가 커져 과적합 영향도도 커짐 |
| boosting[defaultt=gbdt]       | - 부스팅 트리를 생성하는 알고리즘을 기술<br />- gbdf(gradient boosting decision tree), rf(random forest) |
| bagging_fraction[default=1.0] | - 데이터를 샘플링하는 비율 지정<br />- 과적합을 제어         |
| feature_fraction[default=1.0] | - 개별 트리를 학습할 때마다 무작위로 선택하는 피처의 비율<br />- 과적합을 제어 |
| lambda_l2[default=0.0]        | - L2 Regularization 제어를 위한 값<br />- 값이 클수록 과적합 감소 |
| lambda_l1[default=0.0]        | - L1 Regularization 제어를 위한 값<br />- 값이 클수록 과적합 감소 |
| objective                     | 최솟값을 가져야 할 손실함수를 정의                           |
