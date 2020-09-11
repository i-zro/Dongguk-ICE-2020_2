---
layout: post
title: 임베디드 시스템 mid
comments: true
tags: [embedded_system, 임베디드_시스템, 동국대, 김동환교수님]
---

# 20-09-01 (1)

#### # 팀플조는 랜덤하게

#### # 매번 예습 동영상 올라옴

#### # 연락 : 카카오톡

### Lecture 1 Homework & Lab Assignment

<br>

### 수업 계획서

![](2020-09-01-10-21-15.png)

<br>

# Lecture Note 1 Introduction to Xinu

# 20-09-01 (1)

## [Video1 : Lecture Note 1 Introduction to Xinu](https://www.youtube.com/watch?v=PxMe5905_x8&feature=youtu.be)

![](2020-09-01-16-53-10.png)

## Multilevel Structure Of Xinu, A Hierarchial Design

### hierarchial

![](2020-09-03-11-12-12.png)

#### 1. Operating System Services

- Process Manager : 여러 프로그램(process) 동시에 execution 할 수 있도록
- Memory Manager : 메모리 할당
- Device Manager
- Clock (time) Manager
- File Manager
- Interprocess Communication
- Intermachine Communication
- Acoounting

#### 2. Application Programs

API = Interface To System Services

응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스. 주로 파일 제어, 창 제어, 화상 처리, 문자 제어 등을 위한 인터페이스 제공

![](<![](2020-09-01-19-55-36.png).png>)

### socket

프로세스가 네트워크를 통해서 데이터를 주고받으려면 반드시 열어야 하는 창구 같은 것

#### 3. Hardware

## 멀티 태스킹

#### 1. Synchronous event loop

: 우선 순위 정하기의 문제

```c
While(1) {
	Update time-of-day clock;
	if(screen timeout has expired) {
		turn off the screen;
	}
	if(volume button is being pushed) {
		adjust volume;
	}
	if(text message has arrived) {
		Display notification for user;
	}
	…
}
```

#### 2. Asynchronous event loop

![](2020-09-01-20-01-22.png)

#### 3. Concurrent execution

![](2020-09-01-20-01-54.png)

# 20-09-03 (2)

### C 언어 library = 파이썬 package = API

## Video : [Video2 : Lecture Note 1 Xinu Virtual Machine](https://youtu.be/UowGCPFeb7Q)

### Install virtual box

[설치사이트](https://www.virtualbox.org/wiki/Downloads)

- Windows hosts
- VirtualBox 6.1.12 Oracle VM VirtualBox Extension Pack - All supported platforms

두개를 다운 받을 것

### Install xinu

[설치사이트](https://xinu.cs.purdue.edu/)

- A tar file of two appliances that consititute a Virtual Box version (the code works on Vbox 6.1.12)

얘를 받아야함

### 직렬포트 설정 변경

![](2020-09-03-09-31-19.png)
![](2020-09-03-09-32-22.png)

### 초록색 화살표로 시작

![](2020-09-03-09-38-15.png)

- 패스워드 : xinurocks
- 커맨드 창이 나옴

1. 내가 현재 어떤 디렉토리 안에 있는지

```
pwd
```

2. 그 디렉토리 안에 어떤 파일들이 있는지

```
ls
```

3. 현재 실행되고 있는 프로세스

```
ps
```

4. xinu로 디렉토리 옮기기

```
cd xinu
```

- 시스템 프로토콜 확인

```
ls system
```

- library 프로토콜 확인

```
ls lib
```

- tcp/ip 프로토콜 확인

```
ls net
```

- 헤더파일 프로토콜 확인

## xinu 이미지 수정하기

```
cd xinu
```

```
cd compile/
```

```
ls
```

```
make clean
```

해주고 다시

```
make
```

그러면 xinu.elf 파일 생성!

### grep

입력으로 전달된 파일의 내용에서 특정 문자열을 찾고자할때 사용

### tftp

간단한 파일 전송 프로토콜

```
grep tftp Makefile
```

```
ls /srv/tftp/
```

해주면 xinu.boot 파일(이미지) 생성!

## 그 이미지를 backend에서 실행하기

```
sudo minicom
```

- 패스워드 입력
- backend 실행
  ![](2020-09-03-10-35-04.png)
- sudo apt-get update
- sudo apt-get install ctags

# 비디오 렉처노트 2

![LectureNote2_200910_112245_1](https://user-images.githubusercontent.com/48379869/92678497-0e914480-f361-11ea-9da9-b882ff4927ed.jpg)
![LectureNote2_200910_112245_2](https://user-images.githubusercontent.com/48379869/92678500-0f29db00-f361-11ea-9231-b62461be9fac.jpg)
![LectureNote2_200910_112245_3](https://user-images.githubusercontent.com/48379869/92678505-105b0800-f361-11ea-9f0f-85507b7b7179.jpg)
![LectureNote2_200910_112245_4](https://user-images.githubusercontent.com/48379869/92678513-1355f880-f361-11ea-9cf4-76ca556302ed.jpg)
![LectureNote2_200910_112245_5](https://user-images.githubusercontent.com/48379869/92678437-f4576680-f360-11ea-80fe-085829246ead.jpg)
![LectureNote2_200910_112245_6](https://user-images.githubusercontent.com/48379869/92678441-f6b9c080-f360-11ea-9037-4b216999a4f6.jpg)
![LectureNote2_200910_112245_7](https://user-images.githubusercontent.com/48379869/92678446-f91c1a80-f360-11ea-904c-39ecf1a8ef7e.jpg)
![LectureNote2_200910_112245_8](https://user-images.githubusercontent.com/48379869/92678449-f9b4b100-f360-11ea-9159-6b4b30b58e72.jpg)
![LectureNote2_200910_112245_9](https://user-images.githubusercontent.com/48379869/92678450-fae5de00-f360-11ea-9286-8a700cdf0681.jpg)
![LectureNote2_200910_112245_10](https://user-images.githubusercontent.com/48379869/92678452-fc170b00-f360-11ea-9546-5e3d97cbdde1.jpg)
![LectureNote2_200910_112245_11](https://user-images.githubusercontent.com/48379869/92678454-fd483800-f360-11ea-8a0b-fbf7400af653.jpg)
![LectureNote2_200910_112245_12](https://user-images.githubusercontent.com/48379869/92678456-fde0ce80-f360-11ea-926f-02b767c01371.jpg)
![LectureNote2_200910_112245_13](https://user-images.githubusercontent.com/48379869/92678457-ff11fb80-f360-11ea-98ca-f2811591a450.jpg)
![LectureNote2_200910_112245_14](https://user-images.githubusercontent.com/48379869/92678460-ffaa9200-f360-11ea-8c35-74f9b00739bb.jpg)
![LectureNote2_200910_112245_15](https://user-images.githubusercontent.com/48379869/92678462-00dbbf00-f361-11ea-9bc7-9bc09c58e55c.jpg)
![LectureNote2_200910_112245_16](https://user-images.githubusercontent.com/48379869/92678464-020cec00-f361-11ea-8b22-174374cfdb0c.jpg)
![LectureNote2_200910_112245_17](https://user-images.githubusercontent.com/48379869/92678471-0507dc80-f361-11ea-80d3-26c46c15a7b8.jpg)
![LectureNote2_200910_112245_18](https://user-images.githubusercontent.com/48379869/92678475-06390980-f361-11ea-9d62-4e49e85c5374.jpg)
![LectureNote2_200910_112245_19](https://user-images.githubusercontent.com/48379869/92678480-076a3680-f361-11ea-8d49-9c79665c5ada.jpg)
![LectureNote2_200910_112245_20](https://user-images.githubusercontent.com/48379869/92678487-0933fa00-f361-11ea-93d3-da170c4a24aa.jpg)
![LectureNote2_200910_112245_21](https://user-images.githubusercontent.com/48379869/92678491-0c2eea80-f361-11ea-99ed-e65be9948245.jpg)
![LectureNote2_200910_112245_22](https://user-images.githubusercontent.com/48379869/92678495-0d601780-f361-11ea-924a-9c181a43b3a7.jpg)
