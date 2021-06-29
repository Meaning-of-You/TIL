# django 설치

> django를 가상환경에 설치하는 방법 정리



##### 가상환경 활성화

```bash
conda activate <가상 환경 이름>
```

![image-20210629235347950](django_install.assets/image-20210629235347950.png)



##### django 설치

```bash
conda install django
```

![image-20210629235418140](django_install.assets/image-20210629235418140.png)

- Proceed([y]/n)? 이라는 말이 뜨면 y 입력



##### django project 생성

```bash
django-admin startproject <프로젝트 이름>
```

![image-20210629235526417](django_install.assets/image-20210629235526417.png)



##### 생성한 project 위치로 이동

```bash
cd <프로젝트 이름>
```

![image-20210629235538739](django_install.assets/image-20210629235538739.png)



##### server 실행

```bash
python manage.py runserver
```

![image-20210629235605618](django_install.assets/image-20210629235605618.png)

- `ctrl + c`로 빠져나올 수 있음

##### application 생성(추가)

```bash
python manage.py startapp <어플리케이션 이름>
```

![image-20210629235705064](django_install.assets/image-20210629235705064.png)



##### migrations 생성

```bash
python manage.py makemigrations
```

![image-20210629235735627](django_install.assets/image-20210629235735627.png)



##### model 생성

```bash
python manage.py migrate
```

 ![image-20210629235744330](django_install.assets/image-20210629235744330.png)



##### model이 생성되었는지 확인

```bash
python manage.py dbshell
```

![image-20210629235829008](django_install.assets/image-20210629235829008.png)

##### 생성된 table 확인

```bash
.tables
```

![image-20210629235844460](django_install.assets/image-20210629235844460.png)

##### table 정보 확인

```bash 
pragma table_info(테이블 이름);
```

- 순서 | 이름| 형태| not null여부  | pk 여부



##### table 데이터 검색

```bash
SELECT * FROM 테이블 이름;
```



##### sqlite 종료

```bash
.quit
```