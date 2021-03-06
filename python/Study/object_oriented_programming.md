# 객체지향 프로그래밍(object oriented programming)

> python 객체지향 프로그래밍 정리

![인스턴스 - 해시넷](object_oriented_programming.assets/tM-QTaRHGL1wmfFztA9B23oQVrb76BZVRr8cTXQGV9TiPKntgkdFwF4jynBO30aHyAaDs3ZFryW_xh-kQjn952ZsLHFaAEDgt1M-HwQlfM5xFt9Wd9CqrHiHw1Ra1igmc_MfJP3yqO4ko2Zl88x_QDcjJ23RmKZNNNfP0g)

### 객체지향 프로그래밍(object-oriented programming)

객체를 만들고 이용할 수 있는 기능을 제공하는 프로그래밍

- 재사용성이 높음



##### 객체(object)

속성(상태, 특징)과 행위(행동, 동작, 기능)로 구성된 대상

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



##### decorator

함수 이름 앞에 붙여서 사용되며, 기존의 함수 기능을 수정하지 않고 추가적인 기능을 확장해 주는 역할

- callable이면 사용 가능
  - function
  - class(__ init __)
  - instance(__ call __)

- property decorator

  - 메서드를 not callable로 바꿔줌

  ```python
  class A:  
      @property    
      def pd(self):
          return 1
  ```

  ```
  a = A()
  a.pd()
  ```

  ```markdown
  TypeError: 'int' object is not callable
  ```



##### 클래스 내장 모듈

- `__init__()`
  - 객체를 생성하는 것과 동시에 속성값을 지정

```python
class Student():
    
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
stu1 = Student('Tom', 20)
```

- `__new__()`
  -  인스턴스화 할 때 자동으로 실행
- `__class__()`
  - type()과 유사, 객체의 클래스를 알려줌

- `__getattr__()`

  - 정의되어 있지 않은 인스턴스 변수를 호출 할 때 호출

  ```python
  class A:
      def __init__(self,x):
          self.x = x
          self.y = 1
      
      def __getattr__(self, value):
          print('call')
  ```

  ```python
  a.z
  ```

  ```markdown
  out: call
  ```

- `__setattr__ ()`

  - 인스턴스 변수를 설정할 때 사용

- `__delattr__()`

  - 인스턴스 변수를 삭제할 때 사용

- `__dir__()`
  - dir()과 유사하지만 정렬을 함
- `__doc__()`
  - docstring을 의미 
  - 함수나 클래스를 선언할 때, Signature 바로 앞에 따옴표 세개를 이용하여 설명을 기재할 수 있음
- `__dict__()`
  - vars()와 유사, 인스턴스 안에 정의된 값을 dictionary로 보여줌
- `__repr__()`
  - 시스템이 해당 객체를 인식할 수 있는 공식적인 문자열로 나타내줌
- `__str__()`
  - 사용자가 보기 쉬운 형태로 보여줄 때 사용



### 상속

- 클래스에서 이름 뒤에 오는 괄호는 상속
- python의 모든 객체는 object를 상속받음

![1.7: OOP Inheritance - Engineering LibreTexts](object_oriented_programming.assets/inheritance.png)

- 부모 클래스(상위 클래스 혹은 슈퍼 클래스)
- 자식 클래스(하위 클래스 혹은 서브 클래스)
  - 부모 클래스로부터 상속을 받으면 부모 클래스의 속성과 행위를 그대로 이용할 수 있음
  - 부모 클래스에서 정의한 함수 이름과 자식 클래스에서 정의한 함수 이름이 같은 경우 `부모 클래스명.함수명()`이나 `super().함수명()` 사용 

```python
class 자식 클래스명(부모 클래스명):
    <코드 블록>
```

- 파이썬은 부모 클래스가 하나 이상인 다중 상속을 지원함

```python
class 자식 클래스명(부모 클래스1, 부모 클래스2, ...):
    <코드 블록>
```



##### 오버라이딩(overriding)

- 상속받은 자식 클래스에서 상속해준 부모클래스에 이미 정의되어 있는 메서드 기능을 확장해서 정의하도록 하는 것
- 특징
  - 오버라이드할 메서드가 부모 클래스에 정의되어 있어야 함
  - 부모 클래스의 메서드를 자식 클래스에서 사용할 때, 메서드 명이 같아야 함
  - 부모 클래스의 메서드를 자식 클래스에서 사용할 때,  메서드의 파라미터 개수가 같아야 함
  - 부모 클래스의 메서드를 자식 클래스에서 사용할 때,  메서드의 리턴형을 같지 않아도 됨



##### 다형성(polymorphism)

- 상속관계에서 다른 클래스의 인스턴스 객체들이 같은 멤버 함수의 호출에 각각 다르게 반응하도록 하는 것



##### 캡슐화(Encapsulation)

- 필요한 메서드와 멤버를 하나의 단위로 묶어 외부에서 접근 가능하도록 인터페이스를 공개하는 것
- Python에서는 클래스를 정의할 때 멤버 이름에 따라 접근 지정을 설정
  - public(_)
  - private(__)
  - protected



##### 객체지향 메서드

|    메서드    |                 설명                 |
| :----------: | :----------------------------------: |
|    mro()     | 상속 체계의 순서를 알려줌, List 반환 |
| issubclass() |     상속 받았는지의 여부를 확인      |
| isinstance() |         인스턴스 여부를 확인         |
|    vars()    |   인스턴스 안에 정의된 값을 보여줌   |



### Mangling

프로그램에서 함수나 변수를 선언했을때, 선언시 사용했던 이름을 컴파일러가 컴파일 단계에서 일정한 규칙을 가지고 변형하는 것

- 변수/함수 앞에 __를 붙여서 사용
- `_클래스명__변수/함수명` 형태로 바꿔준다.

```python
class A:
    x = 1
    __y = 2
```

```markdown
A._A__y
```

```markdown
out: 2
```

