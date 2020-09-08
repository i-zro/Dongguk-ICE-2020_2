# 20-09-01 (1)

#### # 다음시간에 프로그래밍 환경 잡을 것

#### # 교수님 이메일 연락 : wjhan@dongguk.edu

### # 시험은 가능한 한 대면평가

### # 출석 방식 : O/X 퀴즈

### # 강의 일정

![](2020-09-01-15-20-41.png)

### # 강의자료

http://eshopping.co.kr/

---

![](2020-09-01-15-41-13.png)
![](2020-09-01-15-49-13.png)
![](2020-09-01-15-49-37.png)

#### java 탄생 배경

플랫폼에 대해 독립적인 언어가 필요하다는 요구로 java 탄생

#### 컴파일

소스 파일을 컴퓨터가 이해할 수 있는 기계어로 만드는 과정

#### JRE

개발자가 아닌 경우. 자바 실행 환경. 가상 머신만 있는 것

### JDK

[설치](http://www.oracle.com/technetwork/java/index.html)

자바 응용 개발 환경. 컴파일러 기능

### 자바 API

(Application Programming Interface)
<br>
[설명글 사이트](http://docs.oracle.com/javase/10/docs/api/)
<br>
JDK에 포함된 클래스 라이브러리 (주요한 기능들을 미리 구현한 클래스 라이브러리의 집합)

### 자바 통합 개발 환경 - 이클립스

[설치](http://www.eclipse.org/downloads/)

# 20-09-03 (2)

# New - Java Project 만들기

1. Create module-info.java file 체크 해제
   ![](2020-09-03-15-19-54.png)
2. New - class 생성
3. public static void main(String[] args) 체크
   ![](2020-09-03-15-26-12.png)

# hello world 출력

1. syso + ctrl + 스페이스바

```java
System.out.println("");
```

2. hello world 출력
   - Ctrl + F11 : Run

```java
public class test1 {

	public static void main(String[] args) { //Entry Point : 컴파일의 시작점
		// TODO Auto-generated method stub
		System.out.println("hello world"); // API : 화면에 출력하게 하는 명령어
    }

}
```

# 20-09-08 (3)

### 식별자

클래스, 변수, 상수, 메소드 등에 내가 붙이는 이름
'대소문자 구분해서 영문으로 만든다'

### 키워드

= 예약어
이미 프로그램에서 쓰기로 한 말들

### 변수 기본 타입

- boolean : 1비트 (논리)
- char : 2바이트 (문자)
- byte : 1바이트 (8비트, -128 ~ 127, 정수)
- int : 4바이트

(2비트 = 00 01 10 11 4가지 기분)

### 자동 import

Ctrl + Shift + o

# Scanner 클래스

```java
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int test01;
		// 1. Scanner 준비
		Scanner sc = new Scanner(System.in); // sc : 식별자
		System.out.println("> ");
		test01 = sc.nextInt(); // 대입 (정수 읽기)

		System.out.println(test01);
	}

}
```

```
> 10
10
```
