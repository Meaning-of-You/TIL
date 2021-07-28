# Model Selection 모듈

> scikit-learn의 Model Selection 모듈 정리



### Model Selection 모듈

학습 데이터와 테스트 데이터 세트를 분리하거나 교차 검증 분할 및 평가, Estimator의 하이퍼 파라미터를 튜닝하기 위한 다양한 함수와 클래스 제공



### 학습/테스트 데이터 세트 분리

##### train_test_split()

학습용 데이터의 피처 데이터 세트, 테스트용 데이터의 피처 테이터 세트, 학습용 데이터의 레이블 데이터 세트, 테스트용 데이터의 레이블 데이터 세트를 튜플로 반환

- `test_size`: 전체 데이터에서 테스트 데이터 세트 크기를 얼만큼 sampling 할 것 인가를 결정, 기본값은 25%
- `train_size`:  전체 데이터에서 학습 데이터 세트 크기를 얼만큼 sampling 할 것 인가를 결정
- `shuffle`: 데이터를 분리하기 전 섞을지를 결정, 기본값은 True
- `random_state`: 호출할 때마다 동일한 학습/테스트용 데이터 세트를 생성하기 위해 주어지는 난수 값



### 교차 검증

![Overfitting and underfitting represented using Model error vs complexity plot](https://vitalflux.com/wp-content/uploads/2020/12/overfitting-and-underfitting-wrt-model-error-vs-complexity-300x173.png)

##### 개념

- Overfitting(과적합)

모델이 학습 데이터에만 과도하게 최적화되어, 실제 예측을 다른 데이터로 수행할 경우에는 예측 성능이 과도하게 떨어지는 것

- 교차 검증

데이터 편중을 막기 위해서 별도의 여러 세트로 구성된 학습 데이터 세트와 검증 데이터 세트에서 학습과 평가를 수행하는 것



##### K 폴드 교차 검증

K개의 데이터 폴드 세트를 만들어서 K번만큼 각 폴드 세트에 학습과 검증 평가를 반복적으로 수행하는 방법

- split() 메서드에 인자로 피처 데이터 세트 필요



##### Stratified K 폴드

특정 레이블 값이 특이하게 많거나 매우 적어서 값의 분포가 한쪽으로 치우친 불균형한 분포도를 가진 레이블(결정 클래스) 데이터 집합을 위한 K 폴드 방식

- split() 메서드에 인자로 피처 데이터 세트와 레이블 데이터 세트 필요

- 회귀에서는 지원되지 않음



##### cross_val_score()

교차 검증을 위한 일련의 과정을 한꺼번에 수행해주는 API로, scoring 파라미터로 지정된 성능 지표 측정값을 배열 형태로 반환

- 분할
  - Classifier의 경우, Stratified K 폴드 방식
  - Regressor의 경우, K 폴드 방식
- 파라미터
  -  `estimator`: Classifier 또는 Regressor을 의미
  - `X`: 피처 데이터 세트
  - `y`: 레이블 데이터 세트
  - `scoring`: 예측 성능 평가 지표
  - `cv`: 교차 검증 폴드 수



### GridSearchCV

알고리즘에 사용되는 하이퍼 파라미터를 순차적으로 입력하면서 편리하게 최적의 파라미터를 도출할 수 있는 방안 제공

- 파라미터

  - `estimator`: Classifier 또는 Regressor 또는 Pipeline을 의미
  - `param_grid`: key + 리스트 값을 가지는 딕셔너리, estimator의 튜닝을 위해 파라미터명과 사용될 여러 파라미터 값 지정
  - `scoring`: 예측 성능을 측정할 평가 방법을 지정
  - `cv`: 교차 검증을 위해 분할되는 학습/테스트 세트의 개수 지정

  - `refit`: 가장 최적의 하이퍼 파라미터를 찾은 뒤 입력된 estimator 객체를 해당 하이퍼 파라미터로 재학습, 기본값은 True

- 주요 칼럼

  - `params`: 수행할 때마다 적용된 개별 하이퍼 파라미터값
  - `rank_test_score`: 하이퍼 파라미터별로 성능이 좋은 score 순위
  - `mean_test_score`: 개별 하이퍼 파라미터별로 CV의 폴딩 테스트 세트에 대해 총 수행한 평가 평균값