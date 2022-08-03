---
title: "[JAVA] 클래스명과 파일명은 왜 같아야 하는가?"
excerpt: "JAVA에서 클래스명과 파일명이 같아야 하는 원인에 대해 알아보자."

writer: Dayeong Kim
categories:
  - JAVA
tags:
  - [JAVA, 자바, HelloWorld, 출력, print]

toc: true
toc_sticky: true

date: 2022-08-03
---

해당 게시글은 JAVA로 [Hello World 출력](https://day0522.github.io/posts/JAVA-HelloWorld/)하는 방법을 학습하던 중 **.java 파일의 이름과 내부 클래스명이 같아야 한다**는 사실에 궁금증이 생겨 작성한 글이다.

# 💡 JAVA 클래스명과 파일명은 왜 같아야 하는가?

이는 다음과 같은 이유가 있다고 한다.

![image](https://velog.velcdn.com/images%2Fredgem92%2Fpost%2F161dedf0-de10-46e2-80b4-e929d51dd258%2Fimage.png){: .align-center}{: width="40%" height="40%"}

1. Java 프로그램을 작성할 때는 `.java` 파일로 저장되지만 컴파일 될 때는 `.class` 파일인 바이트 코드를 형성한다. 따라서 **클래스 이름을 파일명과 동일하게 만들면 모호함이 사라진다**는 것이다.

2. **JVM이 해당 클래스를 진입점으로 인식**해야 하기 때문이다. <br> 이때 JVM은 Java Virtual Machine의 줄임말로 `OS에 종속받지 않고 CPU가 JAVA를 인식/실행할 수 있게 하는 가상 컴퓨터`이다.

3. 만약 이름이 다르다면, 소스 파일에 class가 하나 이상인 경우 **JAVA 인터프리터가 해석해야 하는 class와 프로그램의 진입점을 포함하는 class를 쉽게 인식**할 수 없다.

하지만 클래스가 public이 아닌 경우엔 동일하지 않아도 된다고 한다.