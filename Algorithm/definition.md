# 자료구조와 알고리즘

> 자료구조/알고리즘의 정의



### Data Structures

자료의 값 그 자체와 자료들 간의 관계, 자료들에 가해질 수 있는 오퍼레이션들

![Introduction to Data Structures](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/introduction-to-data-structure-classification-6180ea2dcdae970e.png)

##### abstraction(추상화)

수많은 정보들 가운데 어떤 문제를 해결하기 위해서 필수적인 요소만 남겨놓은 채 디테일한 내용들을 제거시키는 과정



##### Primitive Data Structure

programming language에서 가장 기본적으로 제공하는 데이터 구조

- 정수형, 실수형, 문자형 등



##### Non-Primitive Data Structure

- Linear: 자료가 선형으로 펼쳐져 있는 것
  - Stack, Queue
- Non-Linear: 자료의 모양이 선형적이지 않은 모든 것
  - Tree, Graph



### Algorithm

어떤 주어진 입력을 특정한 output으로 변화하는 컴퓨터가 수행할 수  있는 operation들의 sequence

- 모든 가능한 input 인스턴스에 대해서 정답을 내야 함
- 알고리즘이 반드시 종료되어야 함



##### instance

특정 알고리즘에 입력이 되는 데이터

- 알고리즘으로 문제를 해결하기 위해서 필요한 모든 정보가 instance에 포함이 되어 있어야 함



##### sorting 알고리즘

주어진 N개의 숫자들에 대해서 output으로 이 순서가 재배열된 것을 출력으로 내야하는 알고리즘



##### Algorithm Analysis

![시간 복잡도 (빅오, 빅오메가, 빅세타)](https://blog.kakaocdn.net/dn/bPBBiF/btqEBdAApZy/dbheRk89YWJKzAMbG3h0x0/img.png)

- Asymptotic algorithm analysis

어느 정도의 시간을 N대비 소모할 것인가를 시간복잡도 계산

- weak ordering

알고리즘들을 약하게 순서를 매겨보는 것



##### shortest path

![Shortest path problem - Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3b/Shortest_path_with_direct_weights.svg/1200px-Shortest_path_with_direct_weights.svg.png)

그래프 내에서 어떤 경로를 따라가야 가장 가깝게 도달할 수 있는가를 계산



##### minimal spanning tree

![Minimum spanning tree - Wikipedia](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d2/Minimum_spanning_tree.svg/1200px-Minimum_spanning_tree.svg.png)

선택을 함에 있어서 숫자들의 합이 최소가 되도록 선택을 하되 여기 나와있는 모든 엣지들이 다 연결이 되도록 하는 것



##### topological sorting

![Topological Sort Tutorials &amp; Notes | Algorithms | HackerEarth](https://he-s3.s3.amazonaws.com/media/uploads/d6be27e.png)

topological한 상황에서 어떻게 정렬을 할건가에 대한 문제 해결



##### dynamic programming

어떤 큰 문제를 작은 sub-problem들로 나누고 이 sub-problem들을 해결한 결과를 취합해서 최종적으로 하나의 결과를 도출하는 알고리즘의 디자인 방법론

- interval scheduling:  회의실 사용을 최대한 많은 사람에게 overlap없이 할 수 있게 할려면 몇 명에게 우리가 회의실을 사용할 수 있게 하겠느냐 하는 문제 해결

![Five Representative Problems](https://blog.kakaocdn.net/dn/YwvB9/btqJryfSqJ9/XQcOl7qDFNiK1vKK3usfWk/img.png)

- edit distance: 두 문자열이 주어졌을 때 A문자열을 B문자열로 변환하는데 몇 번의 수정이 필요한가라는 문제 해결

![An example of the minimum edit distance algorithm. The left sub-figure... |  Download Scientific Diagram](https://www.researchgate.net/publication/337461648/figure/fig3/AS:828225206902784@1574475685125/An-example-of-the-minimum-edit-distance-algorithm-The-left-sub-figure-show-the-F-matrix.ppm)

- matrix chain multiplication: 어떤 순서대로 매트릭스를 곱하면 계산량을 최소화할 수 있을까 라는 문제 해결

![Matrix Chain Multiplication | DP-8 - GeeksforGeeks](https://media.geeksforgeeks.org/wp-content/uploads/matrixchainmultiplication.png)

