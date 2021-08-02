

## Stacking(스태킹)

> 스태킹 정리



### 스태킹

개별 알고리즘의 예측 결과 데이터 세트를 최종적인 메타 데이터 세트로 만들어 별도의 ML 알고리즘으로 최종합습을 수행하고 테스트 데이터를 기반으로 다시 최종 예측을 수행하는 방식

- 메타 모델: 개별 모델의 에측된 데이터 세트를 다시 기반으로 하여 학습하고 예측하는 방식

![img](https://blog.kakaocdn.net/dn/cM3MVi/btqF3GahzmF/XJjnJf0pUiUkJs0nSEc4y1/img.png)

##### CV 세트 기반의 스태킹

과적합을 개선하기 위해 최종 메타 모델을 위한 데이터 세트를 만들 때 교차 검증 기반으로 예측된 결과 데이터 세트를 이용

![img](https://t1.daumcdn.net/cfile/tistory/99F1CE3359E6E39526)