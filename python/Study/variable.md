# 변수(variable)

> python 변수 정리



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