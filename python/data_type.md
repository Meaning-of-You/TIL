# 변수와 자료형

> python 변수와 자료형 정리



##### 변수(variable)

숫자와 문자 등의 자료(data)를 넣을 수 있는 상자

- 변수는 컴퓨터의 임시 저장 공간(메모리)에 저장

- 파이썬에서는 등호(=)를 이용해 변수에 자료를 할당
  - `variable name = data`

- 변수명 규칙

  - 문자, 숫자, 밑줄 기호(_)를 사용

    - 밑줄 기호(_)로 시작하는 변수명은 특별한 용도에 사용하므로 보통은 시작하지 않음

  - 숫자로 시작할 수 없음

  - 대소문자를 구분함

  - 공백을 포함할 수 없음

  - 예약어는 변수명으로 이용할 수 없음

    - 예약어는 다음과 같이 확인할 수 있음

    ```python
    import keyword
    print(keyword.kwlist)
    ```

    ```markdown
    Out: ['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
    ```



##### 문자열(string)

문자의 나열, 따옴표로 둘러싸인 문자의 집합

- 문자열을 큰 따옴표(")나 작은 따옴표(')로 감싸줌

```python
str1 = 'str test'
str2 = "str test2"
print(type(str1))
print(type(str2))
```

- 변수에 할당한 문자열의 타입은 str

```markdown
out: str 
	 str
```

- 문자열 안에 큰 따옴표(")나 작은 따옴표(')를 포함하는 방법
  - 모두 포함하고 싶거나 문장을 여러행 넣고 싶거나 입력한 그대로 출력하고 싶을때는 문자열 전체를 삼중 큰 따옴표(""")나 삼중 작은 따옴표(''')로 감싸줌

```python
str3 = 'str "test3"'
str4 = "str 'test4'"
print(str3)
print(str4)
```

```markdown
out: str "test3"
     str 'test4'
```

- 문자열은 더하기(+)와 곱하기(*)를 이용할 수 있음

  - 더하기(+): 문자열끼리 연결
  - 곱하기(*): 곱한만큼 문자열 반복

  ```python
  str5 = 'str'
  str6 = 'test'
  str_plus = str5 + str6
  print(str_plus)
  print(str5 * 3)
  ```

  ```markdown
  out: strtest
  	 strstrstr
  ```

  

##### 리스트(list)

