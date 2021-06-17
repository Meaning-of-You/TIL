# SQL 문법

> SQL 기본 문법 정리



### SQL

데이터베이스에서 필요한 형태의 데이터를 추출 또는 가공하기 위해 사용하는 언어

```sql
SELECT 칼럼, 계산 값
FROM 테이블 명
WHERE 조건
GROUP BY 그룹화
HAVING 그룹화에 사용되는 조건
```



##### SELECT

- 칼럼 조회

```sql
SELECT 호출하려는 칼럼
FROM DB명.테이블명;
```

- 집계 함수
  - count
  - sum
  - avg

```sql
SELECT 집계함수
FROM DB명.테이블명;
```

- *(모든 결과 조회)

```sql
SELECT *
FROM DB명.테이블명;
```

- AS

```sql
SELECT 칼럼명 as 변경 칼럼명
FROM DB명.테이블명;
```

- DISTINCT