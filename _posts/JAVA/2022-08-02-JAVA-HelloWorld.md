---
title: "[JAVA] Hello World!!"
excerpt: "JAVA로 Hello World를 출력해보자."

writer: Dayeong Kim
categories:
  - JAVA
tags:
  - [JAVA, 자바, HelloWorld, 출력, print]

toc: true
toc_sticky: true

date: 2022-08-02
---

해당 게시글은 생활코딩 [JAVA1](https://opentutorials.org/module/4294) 강의를 기반으로 하며, 이에 필자의 생각을 추가해 작성한 글이다.

참고로 필자는 지금까지 Cpp, Python을 위주로 공부해온 사람이다.

# 🔍 Hello World 출력하기
모든 언어의 기초가 되는 `Hello World` 출력을 JAVA로 해보려고 한다!

JAVA에서는 아래 코드와 같이 Hello World를 출력할 수 있다.

C++에서 main 함수를 쓰는 것과 같이 정형화 된 문법인 거 같다.

```JAVA : HelloWorldApp.java
public class HelloWorldApp{
    public static void main(String[] args){
        System.out.println("Hello World!!");
    }
}
```

위 코드에서 유의해야 할 점은 다음과 같다.
- 첫 줄의 클래스 이름
- main 함수

# 1️⃣ 첫 줄의 클래스 이름
첫 줄의 클래스 이름을 보면 HelloWorldApp인 것을 볼 수 있다. 이는 필자가 저장한 현재 파일의 이름인 HelloWorldApp.java와 동일하다.

JAVA에서는 **클래스명과 파일명이 동일해야 한다**고 한다.

하지만 궁금해졌다... 도대체 왜?

현재 게시글에 모두 작성하면 내용이 길어지기 때문에 호기심이 생긴다면 [JAVA 클래스명과 파일명은 왜 같아야 하는가?](https://day0522.github.io/posts/JAVA-classname/)를 읽어보길 바란다.

# 2️⃣ main 작성 코드
JAVA의 main 코드에서 `public static void main(String[] args)`는 정형화된 듯하다.

이때 **public**이 쓰이는 이유는 main은 프로그램의 모든 method의 기본이 되기 때문에 모든 곳에서 접근할 수 있어야 하기 때문이다.

또 생긴 궁금증이 괄호 안에 argument가 꼭 있어야 한다는 점이다. 만약에 지우게 되면 error가 발생한다. 그 이유는 main은 프로그램이 시작되는 부분이므로 어떠한 데이터를 넘겨줘야 하는 경우도 있기 때문이다. 즉, **외부에서 값을 받을 수 있게 하기 위함**이다.


---
##### JAVA에 대한 첫 글이다 보니 의지가 불타올라 이런저런 궁금증을 해결하며 학습하려고 했다. 이 의지가 계속 이어가면 굉장히 좋겠다...🙄