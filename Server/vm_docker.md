##  VM
> Virtual Machine 가상 장비

![L: VM,	R: 기본적인 서버](https://miro.medium.com/max/691/1*f1UruRctnWumPcKaPF23AA.png)
- 기본적인 서버의 구조
	- 여러가지 애플리케이션이 실행되는 형태
	- Host 운영체제
	- 물리 장비 (Physical Hardware)
- VM
	- Host 운영체제 위에 마치 별도의 장비가 있는 것처럼 가상의 장비를 만들어 내어 사용하는 것
	- 이때 VM의 운영체제를 Guest 운영체제라고 한다.
- 리젼 : 인스턴스가 위치할 지역(국가/도시 단위) 
	- 물리적으로 독립된 공간이기 때문에 각 영역에 장애가 발생했을 때 영향을 받지 않는다.

## VM vs Docker

![enter image description here](https://www.weave.works/assets/images/bltb6200bc085503718/containers-vs-virtual-machines.jpg)
- **VM**은 Host 운영체제를 위해 완전히 독립적인 Machine을 만들어서 그 위에 **독립적인 Guest 운영체제**를 동작시킨다 → Host 운영체제와 Guest 운영체제 사이에서 가상화 단계를 거치면서 오버헤드가 발생
> 오버헤드(overhead) : 지속적이고 간접적인 비용

- **Docker**(container)는 각각의 Docker 애플리케이션을 마치 ``프로세스`` 처럼 간주한다 → VM에 비해 오버헤드가 적어서 원래의 장비 성능을 발휘
