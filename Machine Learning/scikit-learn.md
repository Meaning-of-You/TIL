# scikit-learn(사이킷런)

> 파이썬 머신러닝 라이브러리 사이킷런 활용



### 머신러닝 개념

##### 지도학습(Supervised Learning)

학습을 위한 다양한 피처와 분류 결정값인 레이블(Lable) 데이터로 모델을 학습한 뒤, 별도의 테스트 데이터 세트에서 미지의 레이블을 예측

= 명확한 정답이 주어진 데이터를 먼저 학습한 뒤 미지의 정답을 예측하는 방식

- 학습 데이터 세트(training dataset): 학습을 위해 주어진 데이터 세트
- 테스트 데이터 세트(test dataset): 머신러닝 모델의 예측 성능을 평가하기 위해 별도로 주어진 데이터 세트

##### 하이퍼 파라미터(Hyper Parameter)

머신러닝 알고리즘 별로 최적의 학습을 위해 직접 입력하는 파라미터

##### 프로세스

1. 데이터 세트 분리: 데이터를 학습 데이터와 테스트 데이터로 분리
2. 모델 학습: 학습 데이터를 기반으로 ML 알고리즘을 적용해 모델 학습
3. 예측 수행: 학습된 ML 모델을 이용해 테스트 데이터 예측
4. 평가: 예측된 결과와 테스트 데이터의 실제 결과를 비교해 ML 모델 성능 평가



### scikit-learn 설치

- conda 명령어

```bash
conda install scikit-learn
```

- pip

```bash
pip install scikit-learn
```



### scikit-learn 모듈

|               분류                |            모듈            | 설명                                                         |
| :-------------------------------: | :------------------------: | :----------------------------------------------------------- |
|            예제 데이터            |      sklearn.datasets      | scikit-learn에 내장되어 있는 dataset                         |
|             피처 처리             |   sklearn.preprocessing    | 데이터 전처리에 필요한 가공 기능 제공(인코딩, 정규화, 스케일링 등) |
|                                   | sklearn.feature_selection  | 알고리즘에 큰 영향을 미치는 피처를 우선순위대로 선택하는 작업을 수행하는 기능 제공 |
|                                   | sklearn.feature_extraction | 텍스트 데이터나 이미지 데이터의 벡터화된 피터를 추출하는데 사용 |
|       피처 처리 & 차원 축소       |   sklearn.decomposition    | 차원 축소(PCA, NMF 등)와 관련한 알고리즘 지원                |
| 데이터 분리, 검증 & 파라미터 튜닝 |  sklearn.model_selection   | 교차 검증을 위한 학습용/테스트용 분리, 그리드 서치로 최적 파라미터 추출 |
|               평가                |      sklearn.metrics       | 분류, 회귀, 클러스터링, 페어와이즈에 대한 성능 측정 방법 제공 |
|            ML 알고리즘            |      sklearn.ensemble      | 앙상블 알고리즘, 랜덤 포레스트, 에이다 부스트, 그래디언트 부스팅 등 제공 |
|                                   |    sklearn.linear_model    | 선형 회귀, 릿지, 라쏘, 로지스틱 회귀, SGD 관련 알고리즘 제공 |
|                                   |    sklearn.naive_bayes     | 나이브 베이즈 알고리즘(가우시안 NB, 다항 분포 NB 등) 제공    |
|                                   |     sklearn.neighbors      | 최근접 이웃 알고리즘(K-NN 등) 제공                           |
|                                   |        sklearn.svm         | 서포트 벡터 머신 알고리즘 제공                               |
|                                   |        sklearn.tree        | 의사 결정 트리 알고리즘 제공                                 |
|                                   |      sklearn.cluster       | 비지도 클러스터링 알고리즘(K-평균, 계층형, DBSCAN 등) 제공   |
|             유틸리티              |      sklearn.pipeline      | 피처 처리 등의 변환과 ML 알고리즘 학습, 예측 등을 함께 묶어서 실행할 수 있는 유틸리티 제공 |

##### 

### 내장 dataset

##### 분류/회귀 연습 데이터

|              API              | 설명                                                         |
| :---------------------------: | ------------------------------------------------------------ |
|    datasets.load_boston()     | 회귀 용도, 미국 보스턴의 집 피처들과 가격에 대한 dataset     |
| datasets.load_breast_cancer() | 분류 용도, 위스콘신 유방암 피처들과 악성/음성 레이블 dataset |
|   datasets.load_disabetes()   | 회귀 용도, 당뇨 dataset                                      |
|    datasets.load_digits()     | 분류 용도, 0~9까지 숫자의 이미지 픽셀 dataset                |
|     datasets.load_iris()      | 분류 용도, 븟꽃에 대한 피처를 가진 dataset                   |

- Key
  - `data`: 피처의 dataset (numpy 배열 타입)
  - `target`: 분류 시 레이블 값, 회귀일 때는 숫자 결과값 dataset (numpy 배열 타입)
  - `target_names`: 개별 레이블의 이름 (numpy 배열/python 리스트 타입)
  - `feature_names`: 피처의 이름 (numpy 배열/python 리스트 타입)
  - `DESCR`: dataset에 대한 설명과 각 피처의 설명 (string 타입)

##### 표본 데이터 생성기

| API                             | 설명                           |
| ------------------------------- | ------------------------------ |
| datasets.make_classifications() | 분류를 위한 dataset 생성       |
| datasets.make_blobs()           | 클러스터링을 위한 dataset 생성 |



### scikit-learn 프레임워크

![img](https://blog.kakaocdn.net/dn/ba5nCh/btqDg4Z5wpb/V070wl7Ns9PML0tkHQgWck/img.png)

##### Estimator

Classifier와 Regressor을 합친 것으로, 지도학습의 모든 알고리즘을 구현한 클래스의 통칭

##### Classifier

분류 알고리즘을 구현한 클래스

##### Regressor

회귀 알고리즘을 구현한 클래스