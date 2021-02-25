# Cookie & Session

|   |Cookie|Session|
|---|:---:|:---:|
|저장위치|Client|Server|
|저장형식|Text|Object|
|만료시점|쿠키 저장시 설정  (설정 없으면 브라우저 종료시)|정확한 시점 모름|
|리소스|클라이언트|서버|
|용량제한|O|X|

### 만료 시점

- 쿠키 : 저장할 때 삭제될 날짜를 정할 수 있음
- 세션 : 클라이언트가 로그아웃하거나, 설정 시간동안 반응이 없으면 무효화

### 리소스

- 쿠키 : 클라이언트에 저장, 클라이언트의 메모리 사용
- 세션 : 서버에 저장, 서버 메모리로 로딩되기 때문에 리소스 차지

### 용량 제한
- 쿠키 : 클라이언트도 모르게 접속되는 사이트에 의하여 설정될 수 있기 때문에 쿠키로 인한 문제가 발생하는 걸 막고자 한 도메인당 20개, 하나의 쿠키당 40KB로 제한
- 세션 : 제한 없음