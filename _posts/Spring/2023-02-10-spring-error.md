---
title: "[Spring] A problem occurred configuring root project '...' 에러 해결 "
excerpt: "A problem occurred configuring root project '...' 에러를 해결해 보자."

writer: Dayeong Kim
categories:
  - Spring
tags:
  - [Spring, Spring Boot, 스프링, 스프링부트, Java, 백엔드, backend, 에러]

toc: true
toc_sticky: true

date: 2023-02-10
---

Spring Initializr를 통해 Spring 프로젝트 파일을 생성하고, build.gradle을 실행하면 다음과 같은 오류가 발생할 때가 있다.

`A problem occurred configuring root project '...'`

이유는 Spring boot 3.x 버전은 JAVA 17부터 지원을 하는데, IntelliJ에서 JAVA 버전이 11로 설정되어 있었기 때문이다.

다음과 같이 설정을 변경함으로써 에러를 해결할 수 있었다.

- Ctrl+Shift+Alt+S를 눌러 JAVA를 17로 변경
- File > Settings > Build, Execution, Deployment > Build Tools > Gradle에서 Gradle JVM의 버전을 JAVA 17로 변경
