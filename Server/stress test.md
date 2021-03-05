### Latency : 지연시간
- HTTP 트랜잭션이 걸리는 시간 (짧으면 짧을수록 성능↑)
> HTTP 트랜잭션 : 요청에서 응답까지의 과정
- 이 시간에는 네트워크 시간 + 애플리케이션에서 처리하는 시간이 포함되어 있기 때문에 0에 가깝게 낮추는 것은 어렵다

### Artillery 스크립트
> CPU 스트레스 테스트 툴
- max : 가장 오래 걸린 요청
- p95 : 전체 HTTP 트랜잭션 중 가장 빠른 상위 95%
- p50 :  전체 HTTP 트랜잭션 중 가장 빠른 상위 50%
- min : 가장 빠르게 온 요청 
> 가급적 전체 HTTP 트래픽을 대표할 정도의 수준인 p99, p95 정도를 많이 사용한다
- ``duation`` 초 동안 ``arrivalRate`` 명의 매초마다 새로운 가상 사용자가 생성

### 실무에서 테스트를 하는 방법
1. 예상 TPS보다 여유롭게 성능 목표치를 잡는다.
> 초당 거래 처리 속도(TPS : Transaction Per Second)
2. API에 기대하는 Latency를 만족할 때까지 성능 테스트
	- 단일 요청에 대한 Latency를 먼저 확인하고 scale-out
	- 기대 Latency 보다 높다면 scale-out으로 해결되지 않음 → 코드가 비효율적이거나, I/0 가 병목, 네트워크에서 오래걸리는 경우
3. Scale-out을 해도 성능이 늘지 않으면 병목을 의심
> 스케일 아웃(Scale out) : 접속된 서버의 대수를 늘려 처리 능력을 향상시키는 것