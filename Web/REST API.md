# REST API

**REST : 웹(HTTP)의 장점을 활용한 아키텍쳐**

- ### REST의 요소
    - Method

        Method	|의미
        :---:|:---:
        POST|Create
        GET	|Select
        PUT	|Update
        DELETE	|Delete
        
    - Resource
        - URI
        - 모든것을 자원(명사)로 표현하고, 세부 자원에는 id를 붙임
    
    - Message
        - 메세지 포맷이 존재 : JSON,XML과 같은 형태

- ### REST의 특징
    - Uniform Interface
        - HTTP 표준만 맞는다면 어떤 기술도 가능한 interface 스타일
        - 특정 플랫폼, 언어, 기술에 종속 받지 않고, 사용 가능한 loosely coupling 구조
    - Statelessness
        - HTTP Session과 같은 컨텍스트 저장소에 상태 정보 저장 안함
        - Request만 Message로 처리하면 되고, 컨텍스트 정보를 신경쓰지 않아도 되므로 구현이 단순
        - REST API 실행 중 실패가 발생한 경우, 트랜잭션 복구를 위해 기존의 상태를 저장할 필요가 있다. (POST Method 제외)
    
    - Resource 지향 아키텍쳐 (ROA)
    - Client-Server Architecture
