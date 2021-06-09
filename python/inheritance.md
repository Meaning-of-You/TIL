# 상속

> python 상속 정리

##### ![1.7: OOP Inheritance - Engineering LibreTexts](inheritance.assets/inheritance.png)

##### 상속

- 부모 클래스(상위 클래스 혹은 슈퍼 클래스)
- 자식 클래스(하위 클래스 혹은 서브 클래스)
  - 부모 클래스로부터 상속을 받으면 부모 클래스의 속성과 행위를 그대로 이용할 수 있음
  - 부모 클래스에서 정의한 함수 이름과 자식 클래스에서 정의한 함수 이름이 같은 경우 `부모 클래스명.함수명()`이나 `super().함수명()` 사용 

```python
class 자식 클래스명(부모 클래스명):
    <코드 블록>
```

