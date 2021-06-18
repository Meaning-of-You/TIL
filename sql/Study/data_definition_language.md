# 데이터 정의어

> SQL 데이터 정의어 정리



![img](data_definition_language.assets/img.jpg)

### 데이터 정의어(DDL)

- Data Definition Language

- DB 구조 정의
- DB 객체 생성/수정/삭제



### CREATE문

테이블을 생성할때 사용

```mysql
CREATE TABLE 테이블명 (
칼럼명 데이터 유형 [NULL|NOT NULL] [DEFAULT 기본값]
[PRIMARY KEY 칼럼명]
[UNIQUE 칼럼명]
[FOREIGN KEY 칼럼명 REFERENCES 테이블명]
);
```

- 데이터 유형

|  분류  |              데이터 유형               |                          저장 유형                           |
| :----: | :------------------------------------: | :----------------------------------------------------------: |
| 문자형 |      CHAR<br />VARCHAR<br />TEXT       | 고정길이 문자열, 남은 공간은 공백으로 채움<br />가변길이 문자열, 남은 공간은 없음 <br />긴 문자열(255자 이상) |
| 정수형 |           INT<br />SMALLINT            |  소수점이 없는 기본 정수형 <br />소수정이 없는 작은 정수형   |
| 실수형 |     DECIMAL<br />FLOAT<br />DOUBLE     | 고정 소수점을 포함한 실수<br />단정도 부동 소수점 실수<br />배정도 부동 소수점 실수 |
| 날짜형 | DATE<br />DATETIME<br />TIME<br />YEAR | 날짜(연도-월-일)<br />날짜시간(연도-월-일- 시:분:초)<br />시간(시:분:초)<br />날짜(연도) |



### ALTER문

테이블을 수정할때 사용

```mysql
ALTER TABLE 테이블명
[ADD|MODIFY] 칼럼명 데이터 유형 [NULL|NOT NULL] [DEFAULT 기본값]
[ADD CONSTRAINT 제약조건명 제약조건 내용]
[DROP COLUMN 칼럼명]
[DROP CONSTRAINT 제약조건명];
```



### DROP문

테이블을 삭제할때 사용

```mysql
DROP TABLE 테이블명;
```



### 뷰(view)

실제 데이터를 저장하지 않는 가상 테이블

##### 뷰 생성

```mysql
CREATE VIEW 뷰 이름 [(칼럼1, 칼럼2, ...)]
AS SELECT 검색문;
```

##### 뷰 삭제

```mysql
DELETE VIEW 뷰 이름;
```



### 인덱스(index)

테이블 안의 데이터를 쉽고 빠르게 찾을 수 있도록 만든 데이터베이스 객체

##### 인덱스 생성

```mysql
CREATE [REVERSE] [UNIQUE] INDEX 인덱스 명
ON 테이블명;
```

##### 인덱스 삭제

```mysql
DROP INDEX 인덱스명 ON 테이블명;
```

