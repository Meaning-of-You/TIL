# 정규 표현식(reqular expression)

> python 정규 표현식 정리



##### 메타문자

원래 그 문자가 가진 뜻이 아닌 특별한 용도로 사용되는 문자

- 매치가 진행될 때 현재 매치되고 있는 문자열의 위치가 변경되는 메타문자

| 메타문자 |                             설명                             |
| :------: | :----------------------------------------------------------: |
|    []    |           문자 클래스, a-z 아무거나 들어가도 매치            |
|    .     |                  \n을 제외한 모든 문자 매치                  |
|    *     |        * 바로 앞에 있는 문자가 0회 이상 반복되면 매치        |
|    +     |       +  바로 앞에 있는 문자가 1회 이상 반복되면 매치        |
|  {m, n}  | m회 이상 n회 이하, {}안에 지정된 숫자 만큼 {} 앞에 있는 문자를 반복 |
|    ?     |                        {0, 1}을 의미                         |

- 문자열을 소모시키는 않는 메타문자

| 메타문자 |                             설명                             |
| :------: | :----------------------------------------------------------: |
|    \|    |                       or 조건식을 의미                       |
|    ^     | 문자열의 처음과 매치<br />MULTILINE을 사용할 경우, 라인별 문자열의 처음과 매치 |
|    $     | 문자열의 끝과 매치<br />MULTILINE을 사용할 경우, 라인별 문자열의 처음과 매치 |
|    \A    | 문자열의 처음과  매치<br />MULTILINE을 사용할 경우, 라인과 상관없이 전체 문자열의 처음과 매치 |
|    \Z    | 문자열의 끝과 매치<br />MULTILINE을 사용할 경우, 라인과 상관없이 전체 문자열의 처음과 매치 |
|    \b    |    단어 구분자, whitespace에 의해 구분된 단어인 경우 매치    |
|    \B    |        whitespace에 의해 구분된 단어가 아닌 경우 매치        |
|    ?     |                      0회 이상 1회 이하                       |
|    \     |         이스케이프 또는 메타 문자를 일반 문자로 인식         |
|    ()    |          그룹핑, 문자열이 계속해서 반복되는지 조사           |



##### 전방탐색

| 정규식 |                             설명                             |
| :----: | :----------------------------------------------------------: |
|   ?    | 긍정형 전방 탐색 <br />해당되는 정규식과 매치되어야 하며 조건이 통과되어도 문자열이 소모되지 않음 |
|   ?!   | 부정형 전방 탐색<br />해당되는 정규식과 매치되지 않아야 하며 조건이 통과되어도 문자열이 소모되지 않음 |



##### re

 python에서 정규 표현식을 지원하는 모듈

- 문자열 검색 메서드

|   메서드   |                          설명                           |
| :--------: | :-----------------------------------------------------: |
|  match()   |       문자열의 처음부터 정규식과 매치되는지 확인        |
|  search()  |     문자열 전체를 검색하여 정규식과 매치되는지 확인     |
| findall()  |      정규식과 매치되는 모든 문자열을 리스트로 리턴      |
| finditer() | 정규식과 매치되는 모든 문자열을 반복 가능한 객체로 리턴 |

- 문자열 변경 메서드

| 메서드 |                             설명                             |
| :----: | :----------------------------------------------------------: |
| sub()  | 정규식과 매치되는 부분을 다른 문자로 변경, 결과를 str로 리턴 |
| subn() |               sub()와 유사, 결과를 튜플로 리턴               |



##### match 객체

match(), search(), findall() 메서드를 수행한 결과로 리턴된 객체

| 메서드  |                      설명                       |
| :-----: | :---------------------------------------------: |
| group() |              매치된 문자열을 리턴               |
| start() |        매치된 문자열의 시작 위치를 리턴         |
|  end()  |         매치된 문자열의 끝 위치를 리턴          |
| span()  | 매치된 문자열의 시작, 끝에 해당하는 튜플을 리턴 |



##### 컴파일 옵션

정규식을 컴파일 할 때 사용되는 옵션

|    옵션    | 약어 |                  설명                   |
| :--------: | :--: | :-------------------------------------: |
|   DOTALL   |  S   | 줄바꿈 문자를 포함하여 모든 문자와 매치 |
| IGNORECASE |  I   |        대소문자와 관계 없이 매치        |
| MULTILINE  |  M   |             여러 줄과 매치              |
|  VERBOSE   |  X   |   verbose 모드를 사용할 수 있도록 함    |



##### Greedy vs Non-Greedy

- Greedy
  - `*`와 `+` 연산자 사용
  - 매치할 수 있는 가장 최대한의 반복을 수행
- Non-Greedy
  - `?`연산자 사용
  - 매치할 수 있는 가장 최소한의 반복을 수행