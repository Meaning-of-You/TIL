# Data Preprocessing(데이터 전처리)

> scikit-learn의 ML 알고리즘을 적용하기 전 Data Preprocessing 정리



### Data Encoding(데이터 인코딩)

##### Label encoding(레이블 인코딩)

카테고리 피처를 코드형 숫자 값으로 변환하는 방식

- 선형 회귀와 같은 ML 알고리즘에는 적용하지 않아야 함

- LabelEncoder 클래스로 구현
  - `classes_`: 문자열 값이 어떤 숫자 값으로 인코딩 되었는지 확인
  - `inverse_transform()`: 인코딩된 값을 다시 디코딩

##### One Hot encoding(원-핫 인코딩)

피처 값의 유형에 따라 새로운 피처를 추가해 고유 값에 해당하는 칼럼에만 1을 표시하고 나머지 칼럼에는 0을 표시하는 방식

- OneHotEncoder 클래스로 구현

- 주의할 점
  - 변환하기 전 모든 문자열 값이 숫자형 값으로 변환되어야 함
  - 입력 값으로 2차원 데이터가 필요
- Pandas의 경우 `get_dummies()`를 이용하여 변환 가능



### feature sacling(피처 스케일링)

서로 다른 변수의 값 범위를 일정한 수준으로 맞추는 작업

##### Standardization(표준화)![img](https://blog.kakaocdn.net/dn/eb41Pu/btqBowKg4pk/HTKoxdu3KHUpVJnAXCyKX0/img.png)

데이터의 피처 각각이 평균이 0이고 분산이 1인 가우시안 정규 분포를 가진 값으로 변환하는 것

- `StandardScaler`: 표준화를 쉽게 지원하기 위한 클래스, 개별 피처를 평균이 0이고 분산이 1인 값으로 변환
  - `SVM`, `Logistic Regression`,`Linear Regression`과 같은 가우시안 분포일 경우 적용

##### Normalization(정규화)

![img](https://blog.kakaocdn.net/dn/b44yeB/btqBqjbY2YC/N8mHlL7dFvZne0zKVWTK3k/img.png)

모두 최소 0~ 최대 1의 값으로 변환하여 개별 데이터의 크기를 모두 똑같은 단위로 변경하는 것

- `MinMaxScaler`: 데이터 값을 0과 1 사이의 범위 값으로 변환 (음수 값이 있으면 -1에서 1값으로 변환)
  - 데이터의 분포가 가우시안 분포가 아닐 경우 적용

##### 유의점

1. 전체 데이터의 스케일링 변환을 적용한 뒤 학습과 테스트 데이터로 분리
2. 테스트 데이터 변환시에는 `fit()`이나 `fit_transform()`을 적용하지 않고 학습 데이터로 이미 `fit()`된 Scaler 객체를 이용해 `transform()`으로 변환



### * 참고

##### fit()

데이터 변환을 위한 기준 정보 설정을 적용

##### transform()

설정된 정보를 이용해 데이터를 변환

##### fit_transform()

fit()과 transform()을 한번에 적용
