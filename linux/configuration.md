# 환경설정

> 가상환경을 생성하고 jupyter 생성하기



### 가상환경 설정

##### 가상환경 확인

```shell
$ conda info --envs
```

![image-20210805202651173](configuration.assets/image-20210805202651173.png)



##### 가상환경 생성

```shell
$ conda create -n [가상환경 이름] python=[파이썬 버전] [사용할 라이브러리]
```



##### 가상환경 활성화

```shell
$ conda activate [가상환경 이름]
```



##### 가상환경 비활성화

```shell
$ conda deactivate
```



### Jupyter Notebook 설정

##### ipykernel 라이브러리 설치

```shell
$ pip install ipykernel
```



##### jupyter notebook에 가상환경 kernel 설치하기

```shell
$ python -m ipykernel install --user --name [가상환경 이름] --display-name [커널 이름]
```



##### jupyter notebook에 가상환경 kernel 삭제하기

```shell
$ jupyter kernelspec uninstall [커널 이름]
```



##### jupyter 실행

```shell
$ jupyter-notebook --ip=0.0.0.0 --no-browser --port=[포트 번호]
```

- 이후 나타나는 링크 복사해서 크롬 브라우저에 붙여넣기

