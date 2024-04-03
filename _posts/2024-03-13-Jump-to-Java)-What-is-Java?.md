---
layout: post
author: Cascal Pascal
tags:
  - language
  - java
  - jump to java
---

>**Course**
>
>[[DevRoad]Java Developer: Jump to Java](https://cascalpascal.github.io/devroad-java-developer)

>**Bookmarks**
>
>- [What is Java?](#what-is-java?)
>
>- [Setting Up Java Development Environment](#setting-up-java-development-environment)


---


# What is Java?
처음에는 가전제품에 탑재해 동작하는 프로그램을 만들기 위해 탄생했으나 지금은 웹과 모바일 앱 개발에서 가장 많이 사용하는 객체 지향 프로그래밍 언어이다.



## Things you can do with Java

- Web programming
  
  인터넷 게시판이나 방명록을 바로 웹 프로그램이라 하며 자바는 이러한 웹 프로그램 개발에 널리 사용된다. 특히 서버 사이드(백엔드) 개발에 강점이 있다. Servlet, JSP, Spring Framework 등과 같은 기술들을 사용하여 웹 프로그램을 개발할 수 있다.

- Android application
  
- Game development
  
  게임 개발을 위한 대표적인 자바 라이브러리로는 Lightweight Java Game Library, 자바 프레임워크로는 libGDX가 있다.

- Database processing
  
  자바는 데이터베이스 시스템에 연결하여 데이터를 관리하는 데 매우 적합한 언어이다.

- Big data and distributed processing
  
  빅 데이터는 대규모의 복잡한 데이터를 의미하며, 전통적인 데이터 처리 방식으로는 분석이 어렵다. 이를 효과적으로 처리하기위해 분산 처리 기술이 사용된다. 자바는 Hadoop, Spark와 같은 빅 데이터 처리에 필요한 도구와 프레임워크를 제공한다.



## Things you can't do with Java

- System Programming
  
- 높은 성능을 요구하는 프로젝트
  
  자바는 Garbage Collection과 just-in-time 컴파일러 같은 기능 때문에 실행 속도가 다소 느릴 수 있다. 따라서 고성능이 중요한 분야에서는 C, C++, 또는 Rust 같은 언어가 적합하다.

> Garbage Collection은 프로그램에서 사용되지않는 메모리를 자동으로 회수하는 메모리 관리 기법이다.
> Just-in-time compiler는 프로그램 실행 시점에 바이트 코드를 기계어로 변환하는 기술이다.

- IOS application

<br>

# Setting Up Java Development Environment



## Installing JDK

JDK(Java development kit)는 자바 코드를 작성하는 도구, 소스를 컴파일하는 컴파일러 등으로 이루어져 있다.

```
$ sudo apt-get update
$ sudo apt-get upgrade

# Java 17 설치
$ sudo apt-get install openjdk-17-jdk
```


## Configuring Environment Variables

```
# 환경 변수 설정
$ sudo gedit ~/.zshrc

# 파일에 JAVA_HOME setting 추가
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
export PATH=$JAVA_HOME/bin/:$PATH
export CLASS_PATH=$JAVA_HOME/lib:$CLASS_PATH

# .zshrc 업데이트
$ source ~/.zshrc

# 잘 적용되었는지 확인
$ echo $JAVA_HOME
```



## Java files and compilation

javac는 java vompiler의 줄임말이다.
자바 프로그램은 확장자가 .java인 파일로 저장되는데, 이는 우리가 작성해야 할 자바 프로그램을 말한다.

만약 MyProgram.java라는 자바 파일을 작성하였고 이를 실행하고 싶다면, 두 단계를 거쳐야 한다. .java 파일을 .class 파일로 바꿔주는 컴파일 단계와 이어서 .class 파일을 실행하는 단계이다. 컴파일을 통해  컴퓨터(그림에서 JavaVM)가 이해할 수 있는 binary file인 .class를 생성해야 프로그램을 실행할 수 있다.

![Java files and compilation(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240313102632.png?raw=true)

**Java는 compile하고 난 후 exe 파일이 아닌 class 파일이 생성된다**

> compile을 통해 exe 파일이 생성되는 C나 C++ 같은 경우엔 JVM 같은 중간 단계를 거치지 않기 때문에 속도가 빠르다. 하지만 운영체제마다 실행 파일을 따로 작성해야 하는 단점이 있다.
> 반면에 자바는 JVM이라는 중간 단계가 있으므로 C나 C++보다 느리지만 한 번 작성한 클래스 파일은 어떤 운영체제에도 사용할 수 있다는 장점이 있다.
> *한 번 작성한 것을 여러 곳에 재활용 하는 것이 자바의 가장 큰 특징이자 장점이라고 할 수 있다.*



## Writing a Simple Program

- 다음과 같은 내용의 helloworld.java 파일을 생성
  
```java
// helloworld.java
public class helloworld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

- .class 파일 생성 및 실행
  
```
# class 파일 생성
$ javac helloworld.java

# 생성되었는지 확인
$ ls

# 생성한 .class 파일 실행
$  java helloworld
```

## main method

어떤 프로그램이든지 시작과 끝이 있는데 이것을 관리하는 것이 main method이다. method는 함수와 동일한 개념이며 class 내의 함수를 보통 method라고 한다. 자바는 모든 것이 클래스 기반이므로 자바에서 사용하는 함수는 모두 method이다.

## 자바의 8가지 특징

1. Simple
   
2. Object-oriented

   숫자(int, float. long 등)나 논릿값(true, false) 같은 원시 자료형을 제외하고 거의 모두 객체로 구성된다.

3. Interpreted
   
4. robust

   포인터 연산을 지원하지 않아 잘못된 주소를 가리킬 가능성을 사전에 없앴다. 모든 메모리 접근을 자바 시스템이 관리하고 제한하며 예외처리까지 하므로 시스템이 붕괴될 우려가 없다.

5. Secured
  
   자바는 프로그램을 작성할 때 자료형 타입에 매우 민감하다. 그래서 자바는 일단 컴파일만 되면 실행할 때 오류 발생률이 현저히 낮다.

6. Platform independent

   자바로 작성한 프로그램이라면 운영체제와 상관없이 어디서든 실행할 수 있다.

7. Multithreaded

   멀티 프로세서 하드웨어를 지원하도록 설계되어 멀티 CPU 시스템에서 효율이 높다.

8. Dynamic

   자바 인터페이스를 이용하면 모듈을 갱신할 때 다른 모듈까지 모두 갱신할 필요가 없다. 인터페이스가 인스턴스 변수와 도구의 실행문을 모두 배제한 채 객체 간의 상호 작용을 정의하기 때문이다.

---

## Reference

https://wikidocs.net/190
