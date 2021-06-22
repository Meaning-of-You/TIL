# java script

> 문서가 동작하도록 하는 java script 정리



### 삽입 방식

`<head>` 영역에 삽입

- 브라우저 렌더링에 방해가 되어 무거운 스크립트가 실행되는 경우 오랫동안 완성되지 못한 화면을 노출

- 문서를 초기화하거나 설정하는 가벼운 스크립트들이 자주 사용

`<body>` 영역에 삽입

- 브라우저가 렌더링이 완료된 상태에서 스크립트가 실행되기에 콘텐츠를 변경하는 스크립트의 경우 화면에 노출된 채로 변화

- 대부분의 스크립트의 위치로 추천되는 위치

```html
<head>
  <script type="text/javascript">
  </script>
</head>
<body>
  <script type="text/javascript">
  </script>
</body>
```



### var

자바 스크립트에서 메모리 공간을 확보하기 위해 변수 선언시 사용

- 규칙
  - 첫번째 문자는 A-Z, a-z, _, $만 사용

  - 나머지 문자는 A-Z, a-z, 0-9를 사용

  - 자바스크립트 예약어는 사용할 수 없음

```html
<script type="text/javascript">
var n1 = 10; 
var n2;

function process() {
  var n3 = 'korea'
  document.write(n1 + " " + typeof(n1) + "<br/>"); 
  document.write(n2+" "+typeof(n2) + "<br/>")
  document.write(n3+" "+typeof(n3) + "<br/>")
}

process();
</script>
```

![image-20210622192037135](java_script.assets/image-20210622192037135.png)



### data type

|      타입       |                             특징                             |
| :-------------: | :----------------------------------------------------------: |
|  숫자(number)   | 자바스크립트는 정수 값과 실수 값을 구분하지 않음<br />모든 숫자는 IEEE 754표준에 의해 정의된 8바이트 크기의 실수로 표현 |
| 문자열(string)  |  유니코드 문자나 숫자, 문장부호들의 시퀀스로 텍스트를 표현   |
| 불리언(boolean) |   참/거짓의 진리 값 두개를 표현, true 또는 false값을 가짐    |
|   배열(array)   | 데이터 값들의 모음<br />배열명 다음에 대괄호( [ ])로 둘러싼 인덱스를 써서 값을 가져올 수 있음 |
|  객체(object)   | 이름이 붙은 값들의 모음, 이름이 붙은 값들을 프로퍼티라고 함<br /> 객체 프로퍼티는 객체명 다음에 점(.)과 프로퍼티명을 붙이거나,<br /> 객체명 다음에 대괄호( [ ])로 둘러싼 프로퍼티명의 문자열을 써서 접근 |
| 함수(function)  | 객체 프로퍼티에 할당 될 수 있는 실행가능한 코드를 가지고 있는 데이터 타입 |
|      null       | 보통 참조 타입과 함께 쓰여 어떠한 객체도 나타내지 않는 특수한 값으로 사용 |
|    undefined    | 변수는 선언되었으나 값이 할당된 적이 없는 변수에 접근하거나, <br />존재하지 않는 객체 프로퍼티에 접근할 경우 반환되는 값 |



### operator

- 산술 연산자

- 문자결합 연산자 (`+`)

- 대입 연산자

- 증감 연산자 (`++`, `--`)

- 비교 연산자 (`===`,` !==`, `==`, `!=`)

```html
<script type="text/javascript">
var x = 10;
var y = '10';
document.write('x==y: '+ (x==y) + "<br/>");
document.write('x===y: '+ (x===y) + "<br/>");
</script>
```

![image-20210622192958995](java_script.assets/image-20210622192958995.png)

- 논리 연산자

- 삼항조건 연산자

- 데이터 타입 연산자 (`typeof`,  `instanceof`)



### statement

##### 선택문

- `if~else`

- `switch~case`

##### 반복문

- `for`
- `while`
- `do~while`
- `for~in`

##### 기타

- `break`



### print

##### document

```html
var v1 = 'java';
var v2 = 'script';
document.write(v1 + '<br/>' + v2);
```

![image-20210622194446566](java_script.assets/image-20210622194446566.png)

##### window

```html
window.alert(v1 + '\n' + v2)
```

![image-20210622194436998](java_script.assets/image-20210622194436998.png)

##### console

```html
console.log(v1 + '  ' + v2)
```

![image-20210622194504193](java_script.assets/image-20210622194504193.png)

