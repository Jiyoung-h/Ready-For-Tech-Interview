# 중앙처리장치(CPU) 작동 원리

### 구성요소

1. 연산 장치 : 산술/논리 연산


- 연산에 필요한 데이터를 레지스터에서 가져오고 연산 결과를 다시 레지스터로 보냄

2. 제어 장치 : 명령어 순서 제어 

- 주기억장치에서 명령어를 꺼내 해독하고 명령어 실행에 필요한 제어 신호를 기억장치, 연산장치, 입출력장치로 보냄
- 장치들은 이 신호를 받아 다음에 수행할 동작을 결정

3. 레지스터 : 고속 기억 장치

- 명령어 주소, 코드, 연산에 필요한 데이터, 연산 결과를 임시로 저장
- 중앙처리장치 종류에 따라 사용할 수 있는 레지스터 개수와 크기가 다름
- 용도에 따라 범용 레지스터와 특수목적 레지스터로 구분
  - 범용 레지스터 : 연산에 필요한 데이터, 연산 결과를 임시로 저장
  - 특수목적 레지스터 : 특별한 용도로 사용
  
  
### 특수 목적 레지스터 중 중요한 것들

- MAR(메모리 주소 레지스터) : 읽기와 쓰기 연산을 수행할 주기억장치 주소 저장
- PC(프로그램 카운터) : 다음에 수행할 명령어 주소 저장
- IR(명령어 레지스터) : 현재 실행 중인 명령어 저장
- MBR(메모리 버퍼 레지스터) : 주기억장치에서 읽어온 데이터/저장할 데이터 임시 저장
- AC(누산기) : 연산 결과 임시 저장

## CPU의 동작 과정

1. **주기억장치**는 입력장치에서 입력받은 데이터 또는 보조기억장치에 저장된 프로그램을 읽어옴
2. **CPU**는 프로그램을 실행하기 위해 주기억장치에 저장된 **프로그램 명령어와 데이터**를 읽어와
처리하고 결과를 다시 **주기억장치**에 저장
3. 주기억장치는 **처리 결과를 보조기억장치에 저장**하거나 출력장치로 보냄
4. **제어장치**는 1~3. 과정에서 **명령어가 순서대로** 실행하도록 각 장치를 제어


### 명령어 세트 : CPU가 실행할 명령어 집합
- ``연산코드(Operation Code) + 피연산자(Operand)``로 이루어짐
- 연산코드 : 연산, 제어, 데이터 전달, 입출력 기능
- 피연산자 : 주소, 숫자/문자, 논리 데이터를 저장

- CPU는 프로그램 실행을 위해 주기억장치에서 명령어를 순차적으로 인출하여 해독하고 실행하는 과정 반복
- CPU가 주기억장치에서 한번에 하나의 명령어를 인출하여 실행하는데 필요한 일련의 활동을
``명령어 사이클`` 이라고 한다.
- 명령어 사이클 : 인출, 실행, 간접, 인터럽트 사이클로 나누어짐

### 인출 사이클과 실행 사이클에 의한 명령어 처리 과정

1. ``PC``에 저장된 주소를 ``MAR``로 전달
2. 저장된 내용을 토대로 주기억장치의 해당 주소에서 명령어 인출
3. 인출한 명령어를 ``MBR``에 저장
4. 다음 명령어를 인출하기 위해 ``PC`` 값 증가
5. ``MBR``에 저장된 내용을 ``IR``에 전달

```
T0 : MAR ← PC
T1 : MBR ← M[MAR], PC ← PC+1
T2 : IR ← MBR
```

### 인출한 이후 명령어를 실행하는 과정

```
T0 : MAR ← IR(Addr)
T1 : MBR ← M[MAR]
T2 : AC ← AC + MBR
```
