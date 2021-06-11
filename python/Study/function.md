# 함수

> python 함수 정리



### 함수의 정의와 호출



##### 함수의 정의

특정 기능을 수행하는 코드의 묶음

- 인자를 통해 함수에 값을 전달



##### 함수의 구조

```python
def 함수명([인자1, 인자2, ...]):
    <코드 블록>
    [return <반환 값>]
```

- 인자도 반환 값도 없는 함수

``` python
def my_func():
    print("Hello Python !!!")
    
my_func()
```

```markdown
out:
Hello Pyrhon !!!
```

- 인자는 있으나 반환 값이 없는 함수

```python
def my_func2(language):
    print("Hello",language)
    
my_func2('python')
```

```markdown
out:
Hello python
```

- 인자도 있고 반환 값도 있는 함수

```python
def my_func3(a, b):
    total = a + b
    return total

my_func3(3,4)
```

```markdown
out:
7
```



##### 매개변수와 인자 사용법

- positional 방식

  - 선언할 때 파라미터 순서와 사용할 때 인자의 입력 순서를 그대로 매칭
  - 값을 안넣으면 기본값이 사용
  - 선언할 때 기본값을 쓰면 그 뒤로 모두 기본값이 있어야 함

  ```python
  def func1(a, b, c=4):
      print(a, b, c)
      
  func1(1,2)
  ```

  ```markdown
  out: 
  1 2 4
  ```

- keyword 방식

  - 순서에 관계없이 파라미터 이름에 따라 값이 대입

  ```python
  def func2(a, b, c):
      print(a, b, c)
      
  func2(b=6, a=3, c=9)
  ```

  ```markdown
  out: 
  3 6 9
  ```

- positional과 keyword 혼합 방식

  ```python
  def func3(a, b, c):
      print(a, b, c)
      
  func3(1, c=3, b=5)
  ```

  ```python
  out:
  1 5 3
  ```

- positional only

  - positional 방식으로만 인자를 입력하도록 강제
  - `/` 앞에 오는 인자들은 positional 방식으로만 입력

  ```python
  def func4(a, b, c,/):
      print(a, b, c)
      
  func4(2,4,6)
  ```

  ```markdown
  out: 
  2 4 6
  ```

- keyword only

  - keyeord 방식으로만 인자를 입력하도록 강제
  - `*` 뒤에 오는 인자들은 keyword 방식으로만 입력 

  ```python
  def func5(*, a, b, c):
      print(a, b, c)
      
  func5(a=7, c=9, b=8)
  ```

  ```markdown
  out: 
  7 8 9
  ```

- 가변 positional

  - `*`를 붙여서 positional 방식으로 입력되는 인자의 개수에 상관없이 모두 받아옴

  ```python
  def func6(*a):
      print(a)
      
  func6(1,3,5)
  ```

  ```markdown
  out:
  1 3 5
  ```

- 가변 keyword

  -  `**`를 붙여서 keyword 방식으로 입력되는 인자의 개수에 상관없이 모두 받아옴

  ```python
  def func7(**a):
      print(a)
      
  func7(a=1, b=3, c=5)
  ```

  ```markdown
  out:
  {'a': 1, 'b': 3, 'c': 5}
  ```

  

##### 변수의 유효  범위

- 지역 변수(local variable)
  - 함수 안에서 정의한 변수
  - 함수 영역 안에서만 동작하는 변수
- 전역 변수(global variable)
  - 함수 밖에서 정의한 변수
  - 코드 내 어디서나 동작하는 변수
- 이름 공간: 변수를 정의할 때 변수가 저장되는 공간
  - 스코핑 룰(Scoping rule): 지역 영역 > 전역 영역 > 내장 영역 순서대로 변수가 있는지 확인
    - 지역 영역(local scope): 지역 변수를 저장하는 이름 공간
    
    - 전역 영역(global scope): 전역 변수를 저장하는 이름 공간
    
    - 내장 영역(built-in scope): 파이썬 자체에서 정의한 이름 공간
    
      

##### 내장 함수

- 형 변환 함수

  |  함수   |                         설명                          |
  | :-----: | :---------------------------------------------------: |
  |  int()  |     실수나 문자열(정수 표시) 데이터를 정수로 변환     |
  | float() | 정수나 문자열(정수 및 실수 표시) 데이터를 실수로 변환 |
  |  str()  |          정수나 실수 데이터를 문자열로 변환           |
  | list()  |         튜플이나 세트 데이터를 리스트로 변환          |
  | tuple() |          리스트나 세트 데이터를 튜플로 변환           |
  |  set()  |          리스트나 튜플 데이터를 세트로 변환           |

- bool 함수

  - 숫자 인자: 0 이외의 숫자는 True, 0은 False 반환
  - 문자열 인자: 문자열이 있으면 True, 문자열이 없으면 False 반환
  - 리스트, 튜플, 세트 인자: 항목이 있으면 True, 항목이 없으면 False 반환

- 기타 함수

  | 함수  |               설명                |
  | :---: | :-------------------------------: |
  | max() |           최댓값을 반환           |
  | min() |           최솟값을 반환           |
  | abs() |           절댓값을 반환           |
  | sum() |          전체 합을 반환           |
  | len() | 항목의 개수(데이터의 길이)를 반환 |

