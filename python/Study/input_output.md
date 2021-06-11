# 입력과 출력(input/output)

> python 입출력 정리



### 화면 출력

##### print()

원하는 내용을 화면으로 출력하기 위한 함수

- 기본 출력

  - `sep`: 문자열 사이의 구분하는 값을 설정

  ```python
  print("Hello","python","!!!", sep = ",")
  ```

  ```markdown
  out: 
  Hello,python,!!!
  ```

  - 줄을 바꾸지 않고 출력하는 방법

  ```python
  print("Hello python", end=" ")
  print("!!!")
  ```

  ```markdown
  out: 
  Hello python !!!
  ```

  

- 형식 지정 출력

  - % 연산자를 이용한 형식 및 위치 지정

  ```python
  language = "python"
  print("Hello %s !!!" %language)
  ```

  ```markdown
  out: 
  Hello python !!!
  ```

  - 형식 지정 문자열에서 출력 위치 지정

  ```python
  lan1 = "python"
  lan2 = "java"
  lan3 = "c"
  
  print("프로그래밍 언어: {}, {}, {}".format(lan1, lan2, lan3))
  ```

  ```markdown
  out: 
  프로그래밍 언어: python, java, c
  ```

  - 형식 지정 문자열에서 숫자 출력 형식 지정

  ```python
  i = 0.123456789
  print("{0:.2f}, {0.5f}".format(i))
  ```

  ```markdown
  out: 
  0.12, 0.12346
  ```

  

### 키보드 입력

##### input()

키보드로 데이터를 입력받기 위한 함수

```python
num = int(input("숫자를 입력하세요: "))
print("입력한 숫자는 %d입니다." % num)
```

```markdown
out: 
숫자를 입력하세요: 10
입력한 숫자는 10입니다.
```



### 파일 읽고 쓰기

##### open()

파일을 여는 함수

```python
f = open('file name', 'mode')
```

- 파일 열기의 속성

| mode |                             설명                             |
| :--: | :----------------------------------------------------------: |
|  r   |                 읽기 모드로 파일 열기(기본)                  |
|  w   | 쓰기 모드로 파일 열기, 같은 이름의 파일이 있으면 기존 내용 모두 삭제 |
|  x   |  쓰기 모드로 파일 열기, 같은 이름의 파일이 있으면 오류 발생  |
|  a   | 추가 모드로 파일 열기, 같은 이름의 파일이 없으면 w와 같은 기능 |
|  b   |                바이너리 파일 모드로 파일 열기                |
|  t   |              텍스트 파일 모드로 파일 열기(기본)              |



##### 파일 쓰기

```python
f = open('file name', 'w')
f.write(str)
f.close()
```

- 파일에 문자열 한 줄씩 쓰기

```python
fw = open('test.txt', 'w') 
for i in range(1,6):
    data = '%d번째 줄입니다.\n' %i
    fw.write(data)
fw.close()
```



##### 파일 읽기

```python
f = open('file name', 'r')
data = f.read()
f.close()
```

- `readline()`: 파일에서 문자를 한 줄 씩 읽어오는 함수

```python
fr = open('test.txt', 'r') 
line1 = fr.readline()
line2 = fr.readline()
print(line1)
print(line2)
fr.close()
```

```markdown
out:
1번째 줄입니다.

2번째 줄입니다.
```

- `readlines()`: 파일 전체의 모든 줄을 읽어서 한 줄씩을 요소로 갖는 리스트로 반환하는 함수

```python
frl = open('test.txt', 'r') 
lines = frl.readlines()
frl.close()
print(lines)
```

```markdown
out:
['1번째 줄입니다.\n', '2번째 줄입니다.\n', '3번째 줄입니다.\n', '4번째 줄입니다.\n', '5번째 줄입니다.\n']
```



##### with 문

수행이 끝난 후 자동으로 파일을 닫아줌

```python
with open('file name', 'mode') as f:
    <코드 블록>
```

```python
with open('test.txt','r') as f:
    for line in f:
        print(line, end="")
```

```mark
out:
1번째 줄입니다.
2번째 줄입니다.
3번째 줄입니다.
4번째 줄입니다.
5번째 줄입니다.
```



