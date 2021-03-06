# 크롤링과 스크레이핑

> 크롤링과 스크레이핑 개념 정리



### 크롤링과 스크레이핑

##### 개념

- 크롤러: 자동으로 웹 페이지에 있는 정보를 수집하는 프로그램
  - 봇, 로봇, 스파이더 라고 부름

- 크롤링: 크롤러로 정보를 수집하는 일

- 스크레이핑: 수집한 정보를 분석해서 필요한 정보를 추출하는것

##### 크롤링과 스크레이핑의 흐름

수집 → 분석 → 추출 → 가공 → 저장 → 출력



### 주의사항

##### 웹 사이트에 접근할 때

- 웹 사이트의 이용 규약을 확인하고 지킴
- robots.txt와 robots 메타 태그의 접근 제한을 지킴
- 제한이 없더라도 상대 서버에 부하가 가지 않을 정도의 속도로 접근
-  rel='nofollow'가 설정돼 있으면 크롤러로 접근하지 않음
- 크롤링을 거부하는 조치가 있으면 즉시 크롤링을 멈추고, 이미 추출한 정보를 모두 삭제



##### 수집한 데이터를 다룰 때

- 저작권에  문제가 있으면 개인적인 용도로만 사용
- 수집한 데이터를 기반으로 검색 서비스를 제공하는 경우, 웹 사이트와 API 등의 사용 규약을 확인하고 문제가 없을 때만 제공
- 이용 규약이 따로 없을 때도 상대방에게 확인한 뒤에 데이터를 공개