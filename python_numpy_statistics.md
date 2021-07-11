## Python vs Numpy 통계

> 합계, 평균, 편차, 분산, 표준편차, 공분산, 상관계수 구하기



### Python

```python
height = [175, 165, 180, 160]
weight = [75, 85, 95, 70]
```



##### 합계

```python
h_sum = sum(height)
w_sum = sum(weight)

print('키 합계:', h_sum)
print('몸무게 합계:', w_sum)
```

```python
out:
키 합계: 680
몸무게 합계: 325
```

##### 평균

```python
h_length = len(height)
w_length = len(weight)
h_mean = h_sum/length
w_mean = w_sum/length

print('키 평균:', h_mean)
print('몸무게 평균:', w_mean)
```

```python
out:
키 평균: 170.0
몸무게 평균: 81.25
```

##### 편차

```python
h_deviation = [i-h_mean for i in height]
w_deviation = [i-w_mean for i in weight]

print('키 편차:', h_deviation, sum(h_deviation))
print('몸무게 편차:', w_deviation, sum(w_deviation))
```

```python
out:
키 편차: [5.0, -5.0, 10.0, -10.0] 0.0
몸무게 편차: [-6.25, 3.75, 13.75, -11.25] 0.0
```

##### 분산

```python
h_data = [(i-h_mean)**2 for i in height]
w_data = [(i-w_mean)**2 for i in weight]
h_variance = sum(h_data)/length
w_variance = sum(w_data)/length

print('키 분산:', h_variance)
print('몸무게 분산:', w_variance)
```

```python
out:
키 분산: 62.5
몸무게 분산: 92.1875
```

##### 표준편차

``` python
import math
math.sqrt

h_st_deviation = math.sqrt(h_variance)
w_st_deviation = math.sqrt(w_variance)

print('키 표준편차:', h_st_deviation)
print('몸무게 표준편차:', w_st_deviation)
```

```python
out:
키 표준편차: 7.905694150420948
몸무게 표준편차: 9.60143218483576
```

##### 공분산

```python
h_w_covariance = [i*j for i, j in zip(h_deviation, w_deviation)]
print(h_w_covariance)

h_w_covariance = sum(h_w_covariance)/length
print(h_w_covariance)
```

```python
out:
[-31.25, -18.75, 137.5, 112.5]
50.0
```

##### 상관계수

```python
h_w_coef = h_w_covariance/(h_st_deviation * w_st_deviation)
print(h_w_coef)
```

```python
out:
0.6587095756740946
```



### Numpy

```python
import numpy as np

height = [175, 165, 180, 160]
weight = [75, 85, 95, 70]
```



##### 합계

```python
h_sum = np.sum(height)
w_sum = np.sum(weight)

print(h_sum)
print(w_sum)
```

```python
out:
680
325
```

##### 평균

```python
h_mean = np.mean(height)
w_mean = np.mean(weight)

print(h_mean)
print(w_mean)
```

```python
out:
170.0
81.25
```

##### 편차

```python
h_deviation = height - h_mean
w_deviation = weight - w_mean

print(h_deviation, sum(h_deviation))
print(w_deviation, sum(w_deviation))
```

```python
out:
[  5.  -5.  10. -10.] 0.0
[ -6.25   3.75  13.75 -11.25] 0.0
```

##### 분산

```python
h_variance = np.var(height)
w_variance = np.var(weight)

print(h_variance)
print(w_variance)
```

```python
out:
62.5
92.1875
```

##### 표준편차

```python
h_st_deviation = np.std(height)
w_st_deviation = np.std(weight)
print(h_st_deviation)
print(w_st_deviation)
```

```python
out:
7.905694150420948
9.60143218483576
```

##### 공분산

```python
h_w_covariance = np.cov(height, weight, ddof=0)
h_w_covariance
```

```python
out:
array([[62.5   , 50.    ],
       [50.    , 92.1875]])
```

##### 상관계수

```python
np.corrcoef(height,weight)
```

```python
out:
array([[1.        , 0.65870958],
       [0.65870958, 1.        ]])
```

