# jenkins
> 빌드를 자동화 해주는 툴, 지속적으로 통합 서비스를 제공하는 툴 (CI tool)
1. 빌드와 배포 (build&deploy)
	- 배포 : 서버에 반영하여 사용자가 사용할 수 있게 하는 것
	- 빌드 : 배포하기 위한 준비 과정, 서버에 올릴 수 있는 상태로 만드는 것
2. 배치 (batch) : 일괄 처리, 주기적으로 처리

###  workflow
![enter image description here](https://t1.daumcdn.net/cfile/tistory/99F26B405A98A93D30)
1. 개발자가 개발을 하고 소스를 git에 커밋한다.
2. Jenkins workspace로 pull 받는다.
3. Docker 이미지를 빌드한다. *( Jenkins의 역할 ! )*
4. 자동 빌드된 Docker 이미지로 테스트 서버에서 테스트를 수행한다.
5. 테스트가 완료되면 해당 이미지를 운영 서버에 배포한다.  

### jenkins instance , work instance
- jenkins 가 work 에 ssh로 접속하여 docker 이미지를 pull 받고 실행시킨다.
	- jenkins만 접근할 수 있도록 비대칭키를 이용한다.


### Docker의 장점
1. 빠른 설치 : 어플리케이션을 설치하고 사용하는 것에 최소의 시간과 용량을 소비한다.
2. 어플리케이션 이식성 : 호스트의 커널이나 플랫폼 버전 등에 상관없이
3. 버전 제어, 컴포넌트 재사용
4. 쉬운 유지관리 : 종속성에 관한 문제들
