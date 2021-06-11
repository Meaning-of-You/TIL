# 함수형 프로그래밍

> python 함수형 프로그래밍 정리



### 함수형 프로그래밍의 기본 원리



##### 순수함수(pure function)

함수의 실행이 외부 상태에 영향을 끼치지 않는 함수

- 부작용(side effect)가 없어야 함
  - `side effect`: 함수의 실행이 외부 상태에 영향을 끼치는 것



##### 람다(lambda) 함수

한줄로 함수를 표현

- 재사용하지 않을 함수를 만들 때 사용해서 익명함수라고 부르기도 함

```python
lambda <인자> : <인자 활용 수행 코드>

(lambda <인자> : <인자 활용 수행 코드>) (<인자>)

lambda_func = lambda <인자> : <인자 활용 수행 코드>
lambda_func(<인자>)
```

```python
(lambda x : x**2) (3)
```

```markdown
out:
9
```



##### 일급 객체 함수(first class function)

함수를 변수나 자료구조에 저장할 수 있는 함수

```python
def plus(a,b):
    return a+b

data = plus
data(2,3)
```

```markdown
out:
5
```



##### 클로저(closure)

함수를 중첩해서 사용하는 기법

```python
def x(a):
    def y():
        return a+10
    return y

result = x(5)
result()
```

```markdown
out:
15
```



#####  고차 함수(higher order function)

function을 인자로 사용하거나 return으로 사용할 수 있는 함수

```python
def num():
    return 5

def num2(i):
    return i

num2(num())
```

```markdown
out:
5
```



### Loop를 사용하지 않는 기법

##### 

##### iterator

순환하면서 객체의 요소를 차례대로 가지고 오는 것

- 사용할 때 마다 하나씩 메모리에 올리는 lazy 기법
  - index, len 사용 불가능
- iterable: 반복문을 수행할 수 있는 객체



##### generator

값들을 갖지 않은 상태에서 하나씩만 데이터를 만들어서 가지고 오는 것

- tuple은 Comprehension이 아닌 generator
  - generator 만드는 방법
    - tuple을 Comprehension처럼 사용
    - yield를 이용



##### Comprehension

iterable한 오브젝트를 생성하기 위한 기법

- List Comprehension

```python
[<표현식> for i in sequence if <조건식>]
```

- Set Comprehension

```python
{<표현식> for i in sequence if <조건식>}
```

- Dict Comprehension

```python
{key:value for key, value in sequence if <조건식>}
```



##### Recursion

함수가 자기 자신을 다시 실행하는 기법

```python
def factorial(n):
    if n == 1:
        return 1
    return n*factorial(n-1)

print(factorial(5))
```

```markdown
out:
120
```



##### 고차함수 기법

- map(함수, 리스트)
  - 리스트 항목마다 함수를 적용

- reduce(함수, 문자열/리스트/튜플)

  - 결과값을 누적해서 연산

- filter(함수, 리스트)

  - 조건에 맞는 항목만 골라냄
  - True이면 남기고, False이면 제거

  

##### 

