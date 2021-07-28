# Evaluation(평가)

> 분류에 사용되는 성능 평가 지표 정리



### 정확도(Accuracy)

실제 데이터에서 예측 데이터가 얼마나 같은지를 판단하는 지표

- 정확도(accuracy)  = `예측 결과가 동일한 데이터 건수 / 전체 예측 데이터 건수`
- 불균형한 레이블 값 분포에서 ML 모델의 성능을 판단할 경우, 적합한 평가 지표가 아님



### 오차행렬(Confusion Matrix)

##### 오차행렬 형태

![ML 평가 지표](https://blog.kakaocdn.net/dn/PcgVI/btqDZNi6bUG/LxH7xucizjhIbrkLo6AwlK/img.png)

이진 분류의 예측 오류가 얼마인지와 더불어 어떠한 유형의 예측 오류가 발생하고 있는지를 함께 나타내는 지표

- `TN`: 예측값을 Negative 값 0으로 예측, 실제 값 역시 Negative 값 0
- `FP`: 예측값을 Positive 값 1로 예측, 실제 값 역시 Negative 값 0
- `FN`: 예측값을 Negative 값 0으로 예측, 실제 값 역시  Positive 값 1
- `TP`: 예측값을  Positive 값 1로 예측, 실제 값 역시  Positive 값 1

##### 주요 지표

- accuracy(정확도): 전체 데이터 중에 예측이 맞는 비율
    `accuracy = (TN+TP)/(TN+FP+FN+TP)`
- pricision(정밀도), PPV(Positive Predictive Value): Positive로 예측한 것 중에서 Positive가 맞는 비율
    `precision = (TP)/(TP+FP)`
- recall(재현율), TPR(True Positive Rate, 민감도): 실제 Positive인 것 중에서 Positive로 예측한 비율
    `recall = (TP)/(TP+FN)`
- F1 Score: pricision(정밀도)와 recall(재현율)의 조화평균
    `F1 Score = 2X(정밀도X재현율)/(정밀도+재현율)`
- specificity(특이성): Negative를 Negative로 예측한 비율
    `TNR = (TN)/(FP+TN)`
- FPR: Negative를 Positive로 예측한 비율
    `FPR = (FP)(TN+FP)`



### 정밀도(Precision)와 재현율(Recall)

##### 정밀도

- 실제 Negative 음성인 데이터 예측을 Positive 양성으로 잘못 판단하게 되면 업무상 큰 영향이 발생하는 경우 중요한 지표
-  TP를 높이기 위해 FP를 낮추는 데 초점을 맞춤

##### 재현율

- 실제 Positive 양성인 데이터 예측을Negative 음성으로 잘못 판단하게 되면 업무상 큰 영향이 발생하는 경우 중요한 지표

-  TP를 높이기 위해 FN을 낮추는 데 초점을 맞춤

##### Trade-off

정밀도와 재현율은 어느 한쪽을 강제로 높이면 다른 하나의 수치는 떨어지기 쉬움

- 정밀도 또는 재현율이 특별히 강조되어야 할 경우 분류의 결정 임곗값(Threshold)를 조정해 수치를 높일 수 있음
- 정밀도와 재현율은 서로 보완적인 지표 → 가장 좋은 성능 평가는 정밀도와 재현율 모두 높은 수치를 얻는 것

##### F1 스코어(score)

정밀도와 재현율을 결합한 지표

- 정밀도와 재현율이 어느 한쪽으로 치우치지 않는 수치를 나타낼 때 상대적으로 높은 값을 가짐



### ROC곡선과 AUC

![ROC Curve(ROC 커브)란? 머신러닝 모형 평가 - 로스카츠의 AI 머신러닝](https://losskatsu.github.io/assets/images/roc/roc03.png)

##### ROC(Receiver Operation Characteristic Curve, 수신자 판단 곡선)

FPR(False Positive Rate)가 변할 때 TPR(True Positive Rate)가 어떻게 변하는지를 나타내는 곡선

- 분류 결정 임겟값을 이용해 FPR을 0부터 1까지 변경하면서 TPR의 변화값을 구함
- 가운데 직선에 가까울수록 성능이 떨어지는 것이며, 멀어질수록 성능이 뛰어난 것

##### AUC(Area Under Curve)

ROC 곡선 밑의 면적을 구한 것으로서 일반적으로 1에 가까울 수록 좋은 수치

- 가운데 직선에서 멀어지고 왼쪽 상단 모서리 쪽으로 가파르게 곡선이 이동할수록 좋은 성능 수치를 얻게 됨