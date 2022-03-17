# 0. Java 
> 혼자 공부하는 자바 - 신용권
# 1. 자바 개발 도구 설치 및 설정

* Oracle JDK 설치
* JAVA_HOME 환경변수 등록
  * 제어판 -> 시스템 -> 고급시스템설정 -> 환경변수 -> 시스템 변수 -> 새로만들기
  * 변수 이름: JAVA_HOME
  * 변수 값: C:Program Files\java\jdk-19.0.1  ( 파일경로 )
* Path 환경 변수 수정
  * 환경변수 -> 시스템 변수 -> 편집 -> 새로만들기 
  * %JAVA_HOME%\bin 입력 -> 맨위로 이동 시키기
* 이클립스 설치
  * exe파일 -> 권리자 권한으로 실행 -> Eclipse IDE for Enterprsise Java and ... 클릭
  * 설치폴더 -> C:\Program Files -> Install -> Launch -> Launch
* 퍼스펙티브와 뷰
  * eclipse 실행 -> window -> perspective -> open perspectiv -> java
* 프로젝트 생성, Java SE 모듈
  * 프로젝트 생성 -> module-info.java 파일-> 중괄호안에 requires java.se; 입력 후 저장.
  * 프로젝트의 src폴더 -> new -> package -> name 입력 -> finish
  * 생성한 package 우클릭 -> new -> class -> name 입력 -> public static void main 체크 -> finish
<hr>

# 2. 변수와 타입
* 핵심 키워드
  * 2-1. 변수, 변수선언, 변수사용, 변수범위
  * 2-2. 정수타입, 실수타입, char타입, string타입, boolean 타입
  * 2-3. 자동타입변환, 강제타입변환, Integer.parseInt(), Double.parseDouble(), string.valueOf()
  * 2-4. System.out.println(), System.out.printf(), System.in.read(), Scanner
<hr>

## 2-1. 변수
* 변수는 값을 저장할 수 있는 메모리의 특정 번지에 붙이는 이름.
* 변수가 초기화 되면 메모리 번지 정보를 갖고, 해당 메모리 번지에 값이 저장됨.
* 정수타입의 변수에는 정수타입만, 실수타입의 변수에는 실수타입만 저장할 수 있음.
* 모든 변수는 중괄호 {} 블록 내에서 선언되고 사용됨.
* 메서드 블록 내에서 선언된 변수는 로컬 변수라고 부름.
* 로컬 변수는 메서드 블록 내부에서만 사용되고 메서드 실행이 끝나면 메모리에서 없어짐.
<hr>

## 2-2. 기본 타입

| 저장되는 값에 따른 분류 | 타입의 종류 | 
|---|:---:|
| 정수 타입 | byte, char, short, int, long |
| 실수 타입 | float, double |
| 논리 타입 | boolean |

### 2-2-1. 정수타입

| 타입 | 메모리 사용 크기 | 
|---|:---:|
| byte | 1byte |
| short | 2byte |
| char | 2byte |
| int | 4byte |
| long | 8byte |
  * 정수 리터럴
    * 소스 코드에서 프로그래머에 의해 직접 입력된 값을 리터럴 이라고 부름.
    * 2진수: 0b, 0B로 시작.
    * 8진수: 0으로 시작.
    * 16진수: 0x로 시작.
  * long타입 변수에 정수 리터럴을 저장할때 범위가 int 타입의 범위를 넘는다면 뒤에 L을 붙여야 함.
  * char 타입
    * char 타입은 음수를 가질 수 없음.
    * 하나의 문자를 작은따옴표(')로 감싼 것을 문자 리터럴이라 함.
    * 문자 리터럴은 유니코드로 변환되어 저장됨.
  * string 타입
    * 큰따옴표(")로 감싼 문자들을 문자열이라 함.
    * 문자열을 변수에 저장할땐 string 타입을 사용해야함.
* 이스케이프 문자
  * \(역슬래시)를 사용함.
  * \" : `string str = " hello \"java" ";         // 출력: hello "java" `
  * \' : ' 출력
  * \\ : \ 출력
  * \t : 탭만큼 띄우기
  * \n : 개행
<hr>

### 2-2-2. 실수타입

| 타입 | 메모리 사용 크기 | 
|---|:---:|
| float | 4byte |
| double | 8byte |
  * 실수 리터럴
    * 소스코드에서 소수점이 있는 숫자 리터럴은 10진수 실수로 인식.
    * e, E가 포함 되어 있는 숫자 리터럴은 10진수 실수로 인식.
    * 자바는 실수 리터럴을 기본적으로 double 타입으로 해석하므로 double 타입 변수에 저장해야함.
    * 실수 리터럴을 float 타입으로 저장하려면 리터럴 뒤에 f, F를 붙여야 함.
<hr>

### 2-2-3. 논리타입
* 논리 리터럴로 ture, flase를 사용.
* 논리 리터럴은 boolean 타입 변수에 저장.
* ` boolean stats = false ; `

<hr>

## 2-3. 타입 변환
* 데이터 타입을 다른 데이터 타입으로 변환하는 것.
### 2-3-1. 자동 타입 변환
* 자동으로 타입 변환이 일어나는 것.
* 값의 허용 범위가 작은 타입 -> 큰 타입으로 저장될 때 발생.
* 정수타입 -> 실수타입으로 저장될때 발생.
* byte -> char 타입은 변환 되지 않음. char 타입의 범위는 음수를 포함하지 않기 때문.
### 2-3-2. 강제 타입 변환
* 큰 범위 타입 -> 작은 범위 타입으로 저장할 때.
* 실수타입 -> 정수타입으로 변환 할 때.
* `작은 범위 타입 = (작은 범위 타입) 큰 범위 타입 `
* ` byte byteValue = (byte) intValue; `
* ` int intValue = (int) DoubleValue; `
### 2-3-3. 정수 연산에서의 자동 타입 변환
* int 타입보다 작은 byte, short가 산술 연산식에서 피연산자로 사용되면 자동으로 int 타입으로 변환됨.
* int 타입보다 허용 범위가 큰 long 타입일 경우 다른 피연산자는 자동으로 long 타입으로 변환됨.
```java
byte x = 10;
byte y = 20;
byte result = x + y;   // 컴파일 에러
int result = x + y;    //  byte변수 int타입으로 변환되었으므로 int 타입으로 저장해야함.
```
### 2-3-4. 실수 연산에서의 자동 타입 변환
* 실수 타입 변수가 동일한 타입이라면 해당 타입으로 연산됨.
* double 타입 변수와 다른 타입 변수는 모두 double 타입으로 변환 되어 연산을 수행함.
### 2-3-5. + 연산에서의 문자열 자동 타입 변환
* 피연산자가 모두 숫자일 경우 덧셈 연산을 수행.
* 피연산자 중 하나가 문자열일 경우에는 나머지 피연산자도 문자열로 자동 변환되어 연산을 수행.
<hr>

### 2-3-6. 문자열 -> 기본타입으로 강제 타입 변환
* parseByte, parseShort, parseInt, parseLong, parse Double ...
```java
string str = "30";
int value = Integer.parseInt(str);
short value1 = Short.parseInt(str);
byte value2 = Byte.parseByte(str);
Double value3 = Double.parseDouble(str);
```
### 2-3-7. 기본타입 -> 문자열로 강제 타입 변환
* string.valueOf()
* ` string str = String.valueOf(기본타입값); `
<hr>

## 2-4. 변수와 시스템입출력
* 핵심 키워드
  * System.out.println()
  * System.out.print()
  * System.out.printf()
  * System.in.read()
  * Scanner
### 2-4-1. 모니터로 변수값 출력하기.
* System.out.println() : 괄호안의 내용을 출력하고 개행.
* System.out.print() : 괄호안의 내용을 출력.
* System.out.printf("형식문자열", 값1, 값2 ...) : 괄호안의 첫 번째 문자열 형식대로 내용을 출력.
  * ex) ` System.out.printf("이름: %s", "홍길동");    // 이름:김자바 , 형식문자열 %s 사용 `
  * ex) ` System.out.printf("나이: %d", 25);          // 나이:25 , 형식문자열 %d 사용 `
| 형식문자열 | 설명 | 
|---|:---:|
| %d | 정수 |
| %f | 실수 |
| %s | 문자열 |
| %c | 문자 |
### 2-4-2. 키보드에서 입력된 내용 변수에 저장하기.
* System.in.read() : 키코드를 하나씩 읽음. 통 문자열로 읽지 못함.
```java
int keyCode = System.in.read();                      // a 입력
System.out.println("keyCode: " + keyCode);           // keyCode:97
```
* 입력받은 문자열 저장하기.
```java
package sec01.exam01;

import java.util.Scanner;                             // java.util 을 import해야함. 

public class VariableInitializationExample {

	public static void main(String[] args) throws Exception {
    Scanner scanner = new Scanner(System.in);             
    string inputData = scanner.nextLine();               // scanner.nextLine() 를 사용해 입력받은 값을 inputData에 저장.
    gi
    System.out.println("입력된 문자열: " + inputData);
	}
}
```
<hr>

## 3. 연산자
* 핵심키워드
  * 3-1. 연산자, 피연산자, 연산방향, 연산 우선순위
  * 3-2. (증감, 비교, 논리, 대입, 삼항) 연산자
* 삼항연산자 
  * (조건식) ? true일때 : false일때

<hr>

## 4. 조건문과 반복문
* 핵심키워드
  * 4-1. if문, if else문, switch문
  * 4-2. for문, wihle문, do wihle문, break문, continue문
### 4-1. 조건문
* if문, if-else문, 
  * `if(조건값)` 조건값이 true면 if문 실행, false면 esle문 실행.
  ```java
  if(조건값){
    ...
  }
  else if{
    ...
  }
  else{
    ...
  }
  ```
* switch문
  * `switch(변수)` 변수가 어떤 값을 갖느냐에 따라 실행문이 선택됨.
  ```java
  swich(변수){
    case 변수값:
      ...
      break;
    case 변수값:
      ...
      break;
    default:
      ...
      break;
  }
  ```
<hr>

### 4-2. 반복문
* for문
```java
for(초기화식; 조건식; 증감식){   //순서: 초기화식-> 조건식-> 실행문-> 증감식.
  ...
}
```
* while문
```java
while(조건식){
  ...
}
```
* do while문
```java
do{
  ...
}while(조건식)   // 한번은 무조건 실행한다는 특징.
```
* break문, continue문
  * break문은 조건문, 반복문을 종료하고 완전히 빠져나간다.
  * continue문은 반복문에서 사용되는데 조건식으로 다시 이동시킨다.
<hr>

## 5. 참조타입
* 핵심키워드 : 기본타입, 참조타입, 메모리 사용 영역, 번지비교, null, NullPointerException
<hr>