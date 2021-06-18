# SQL과 Python 연동

> sql과 python 연동하는 방법



### DB 연동하기



##### 1. 모듈 설치

```python
!pip install pymysql
```



##### 2. 모듈 임포트

```python
!pip install pymysql
import pymysql
```



##### 3. DB 접속하기

```python
conn = pymysql.connect(host='DB IP name',
                       port=port number,
                       user='user name', 
                       passwd='password', 
                       db='DB')
```



##### 4. 데이터 받아오기

```python
cur = conn.cursor()

sql = "SELECT * FROM DB"
cur.execute(sql)
```



##### 5. 결과 불러오기

- `fetchone()`: 하나의 row만 리턴
- `fetchall()`: 결과를 모두 리턴
- `fetchmany(rows num)`: rows의 숫자만큼 리턴 

```python
result = cur.fetchone()
print(result)
```



##### 6. DB 접속 종료하기

```python
conn.close()
```



### 데이터 수정하기

- `excute()`: 단일성 입력, 하나의 레코드 입력
- `excutemany()`: 배치 처리, 여러개의 레코드 입력



##### UPDATE

```python
cur = conn.cursor()
data = {"컬럼1": 변경값1, ... }

sql = "UPDATE 테이블명 SET 컬럼1=%(변경값1)s, ... WHERE 조건식"

cur.execute(sql, data)
conn.commit()
```



##### INSERT

```mysql
cur = conn.cursor()
data = {컬럼1, 컬럼2, ...}

sql = "INSERT INTO 테이블명(컬럼1, 컬럼2, ...) VALUES (%s, %s, ...)"
cur.execute(sql, data)
conn.commit()
```



##### DELETE

```mysql
cur = conn.cursor()

sql = "DELETE FROM 테이블명 WHERE 조건식"
cur.execute(sql)
conn.commit()
```

