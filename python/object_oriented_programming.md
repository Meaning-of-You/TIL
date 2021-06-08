# 객체지향 프로그래밍

> python 객체지향 프로그래밍 정리

![인스턴스 - 해시넷](object_oriented_programming.assets/tM-QTaRHGL1wmfFztA9B23oQVrb76BZVRr8cTXQGV9TiPKntgkdFwF4jynBO30aHyAaDs3ZFryW_xh-kQjn952ZsLHFaAEDgt1M-HwQlfM5xFt9Wd9CqrHiHw1Ra1igmc_MfJP3yqO4ko2Zl88x_QDcjJ23RmKZNNNfP0g)

##### 객체(object)

속성(상태, 특징)과 행위(행동, 동작, 기능)로 구성된 대상

- 객체지향 프로그래밍(object-oriented programming): 객체를 만들고 이용할 수 있는 기능을 제공하는 프로그래밍 언어

- 속성은 변수로, 객체가 할 수 있는 행동은 함수로 구현
- 객체를 클래스의 인스턴스(instance)라고 함



##### 클래스(class)

객체의 공통된 속성과 행위를 변수와 함수로 정의한 것

```python
class 클래스명():
    [변수 1]
    [변수 2]
    
    def 함수1(self[, 인자1, 인자2, ...]):
        <코드 블록>
```

- 클래스명은 보통 알파벳 대문자로 시작

- 클래스에서 정의한 함수의 첫 번째 인자는 self

  - `self`: 객체 생성 후에 자신을 참조하는데 이용
    - 클래스의 객체 자신을 가리킴

  

##### 객체 생성 및 활용

```python
class Student():
    pass
```

- 객체를 생성하는 방법

  - 객체명 = 클래스명()

  ```python
  stu1 = Strudent()
  ```

- 객체에 속성을 설정하는 방법

  - 객체명.변수명 = 속성값

  ```python
  stu1.name = "Tom"
  ```

- 객체의 속성을 가져오는 방법

  - 객체명.변수명

  ```python
  print("이름:", stu1.name)
  ```

  ```markdown
  out:
  이름:Tom
  ```

- 객체의 메서드를 호출하는 방법

  - 객체명.메서드명([인자1, 인자2, ...])



##### 객체 초기화

- `__init__()`: 객체를 생성하는 것과 동시에 속성값을 지정

```python
class Student():
    
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
stu1 = Student('Tom', 20)
```



##### 클래스에서 사용하는 변수

- 클래스 변수
  - 클래스 내에 있지만 함수 밖에서 `변수명 = 데이터` 형식으로 정의한 변수
  - 클래스에서 생성한 모든 객체가 공통으로 사용할 수 있음
- 인스턴스 변수
  - 클래스 내의 함수 안에서 `self.변수명 = 데이터` 형식으로 정의한 변수
  - 각 인스턴스에서 개별적으로 관리
  - 클래스 내의 모든 함수에서 `self.변수명` 으로 접근



##### 클래스에서 사용하는 함수

- 인스턴스 메서드

  - 각 객체에서 개별적으로 동작하는 함수를 만들고자 할 때 이용

  ```python
  def 함수(self[, 인자1, 인자2, ...]):
  	self.변수명1 = 인자1
      self.변수명2 = 인자2
      ...
  ```

  ```python
  객체명 = 클래스명()
  객체명.메서드명([인자1, 인자2, ...])
  ```

- 정적 메서드

  - 클래스와 관련이 있어서 클래스 내에 두기는 하지만 클래스나 클래스의 인스턴스와는 무관하게 독립적으로 동작하는 함수를 만들고자 할 때 이용

  ```python
  @staticmethod
  def 함수([인자1, 인자2, ...]):
  	<코드 블록>
  ```

  ```python
  클래스명.메서드명([인자1, 인자2, ...]):
  ```

- 클래스 메서드

  - 클래스 변수를 사용하고자 할 때 이용

  ```python
  @classmethod
  def 함수(cls[, 인자1, 인자2, ...]):
  	<코드 블록>
  ```

  ```python
  클래스명.메서드명([인자1, 인자2, ...]):
  ```

