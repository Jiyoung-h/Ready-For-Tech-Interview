## Java와 C/C++ 실행 환경 및 실행 과정
| Java |  C/C++|
|--|--|
|  링커 X 컴파일러 O | 링커 O 컴파일러 O |
|  바이트 코드 생성| 실행 파일 생성 |
|자바 가상 기계에서만 실행 가능 (독립적)|플랫폼에 종속적|

## Java의 특징
- 객체 지향
	- 클래스 계층 구조
	- 상속성
	- 다형성
	- 캡슐화
- 멀티스레드
	- 하나의 프로그램에 다수의 스레드가 동시에 실행
	- 운영체제의 도움 없이 멀티스레드 프로그래밍
- 플랫폼 독립성
- 소스와 클래스 파일
	- .java → 컴파일 → .class
- 실행 모듈
	- 다수의 클래스 파일을 jar 형태로 압축하여 배포 및 실행
- 클래스로 캡슐화
	- 변수나 메소드는 반드시 클래스 내에 구현
- 패키지 구조

### 자바 프로그램의 구조
- 클래스(class) > main( ), 메소드(method)
### 자바의 데이터 타입
- 기본 타입 : 8개
1. boolean
2. char
3. byte
4. short
5. int
6. long
7. float
8. double
- 문자열은 기본 데이터 타입에 속하지 않는다. String 클래스를 이용
### 정수 타입 리터럴
- 8진수 : 0으로 시작
- 16진수 : 0x으로 시작
- 10진수 : 0으로 시작하지 않는 수
- 2진수 : 0b로 시작
- 모든 정수 타입 리터럴은 int 타입으로 처리한다.
	- long 타입으로 하고자 한다면 숫자 뒤에 L 또는 l 을 붙이면 된다.
### 실수 타입 리터럴
: 부동 소수점을 갖는 수
- 모든 실수 타입 리터럴은 double 타입으로 처리한다.
	- float 타입으로 하고자 한다면 숫자 뒤에 F 또는 f 을 붙이면 된다.
(ex) ``float w = 0.1234; // 컴파일 오류``

### null 리터럴
> null은 어떤 레퍼런스 타입의 값으로도 사용될 수 있고, 기본 타입을 제외한 어떠한 타입 변수에도 대입될 수 있다.
```
int n = null; 		// 오류
String s = null;	// 정상
```
###  상수
: final 키워드를 사용
- 한번 초기화 된 다음에 상수 값은 변경할 수 없다.

### 타입 변환
- 자동 타입 변환 : 작은 데이터 타입에서 큰 데이터 타입으로 변환하면 손실 없이 그대로 보존
```
byte >> short/char >> int >> long >> float >> double
```
- 강제 타입 변환 : 큰 데이터 타입에서 작은 데이터 타입으로 변환하면 데이터 손실이 발생

### 자바에서 키 입력
1. ``System.in`` : 원시적인 저수준 입력 스트림 객체
```
InputStreamReader rd = new InputStreamReader(System.in);
int a = rd.read();
```
2. ``Scanner`` 클래스를 이용한 키 입력
- 객체 생성 ``Scanner scanner = new Scanner(System.in);``
- import문 ``import java.util.Scanner``
```
사용자의 키 입력 : kim seoul 33 65.1
Scanner scanner = new Scanner(System.in);
String name = scanner.next();	// name = "kim"
String addr = scanner.next();	// addr = "seoul"
int age = scanner.nextInt();	// age = 33
double weight = scanner.nextDouble();	// weight = 65.1
```
- 메소드 종류
```
String next()
String nextLing() : 한 라인 전체 ('\n' 까지)
int nextInt() : (byte, short, long, float, double 도 같은 형식)
```

### 배열
1. 배열에 대한 레퍼런스 변수 선언
``int a []; 또는 int[] a;``
2. 배열 생성
``a = new int [5];``


	1+2. 배열의 선언과 동시에 생성
``int a[] = new int[5];``
3. 배열 초기화
``int a[] = {0, 1, 2, 3, 4};``


- 배열 참조
```
int a[] = new int[5];
int b[] = a;
```
두 개의 레퍼런스가 하나의 배열을 참조하고 있다.
- for-each 문
	- ``for(String s : names)`` : s 는 names[0], names[1], ...
	- ``for(Week day : Week.values())`` : day는 enum Week의 원소

- 비정방형 배열 : 행마다 열의 개수가 서로 다른 배열
```
int i[][];
i = new int[4][];	// 행은 4개
i[0] = new int [1];	// 첫번째 행은 1열
i[1] = new int [4];	// 두번째 행은 4열
...
```
- 메소드에서 배열 리턴
```
int[] arrayMethod(){
	int temp[] = new int[4];
	return temp;
}
```


### main( ) 메소드의 특징
``public static void main(String[] args)``
- public : 다른 클래스에서 호출 가능
- static : 클래스 객체가 생성되기 전에 자바 가상 기계에 의해 호출
- void : 반환값 없음
- String[] args : 모든 인자를 문자열로 처리

## 자바의 예외 처리
> 예외 (Exception) : 프로그램 실행 중에 발생하는 런타임 오류를 처리하는 방법
### 예외 처리
```
try {
	예외가 발생할 가능성이 있는 실행문
}
catch(처리할 예외 타입 선언) {
	예외 처리문
}
finally {
	예외 발생 여부와 상관없이 무조건 실행되는 문장
}

```
### 예외 종류
-`` ArithmeticException`` : 정수를 0으로 나눌 때 발생
- ``NullPoineException`` : null 레퍼런스를 참조할 때 발생
- ``ClassCastException`` : 변환할 수 없는 타입으로 객체를 변환할 때 발생
- ``OutOfMemoryException`` : 메모리가 부족한 경우 발생
- ``ArrayIndexOutOfBoundsException`` : 배열의 범위를 벗어난 접근시 발생
- ``IllegalArgumentException`` : 잘못된 인자 전달 시 발생
- ``IOExceptionException`` : 입출력 동작 실패
- ``NumberFormatException`` : 문자열이 나타내는 숫자와 일치하지 않는 타입의 숫자로 변환시 발생
  - ex) 문자열을 정수로 변환할 때 부동소수점 값이 들어가면 발생한다.
