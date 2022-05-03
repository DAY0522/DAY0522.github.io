---
title: "[Web] 웹이란 무엇인가?"
excerpt: "웹을 공부하기 위한 기초 지식을 알아보자."

writer: Dayeong Kim
categories:
  - Web
tags:
  - [Web, http, https, resource, URL, URI, encoding, URI 구성 요소]

toc: true
toc_sticky: true
 
date: 2022-05-02
last_modified_at: 2022-05-03
---

학과 복지를 위한 웹 사이트 프로젝트에 지원하기 위해 백엔드에 대한 공부가 필요했다. 이를 위해 백엔드 스터디를 신청했으며, 본격적으로 백엔드 공부를 하기에 앞서 웹에 대해 공부하고자 한다.  

# 1. 웹이란 무엇인가?
`웹(Web)`을 공부하기 위해 기본적인 용어에 대해 알아보자.  

- `웹(Web)` : 인터넷상의 서비스 중 **HTTP**를 이용하여 정보를 공유하는 통신 서비스  
- `웹 서버(Web Server)`
  - 사용자가 어떻게 호스트 파일들에 접근하는지를 관리 
  - 주소 HTTP 프로토콜을 사용하여 클라이언트의 요청을 처리 및 응답
- `웹 클라이언트(Web Client)` : 서비스를 받는 사용자  

# 2. 데이터를 주고받는 과정의 원리 및 기술
사용자(웹 브라우저)와 웹 서버가 데이터를 주고받는 과정의 원리와 기술을 단계별로 알아보자.  
## 📌 Web Browser(웹 브라우저)
> *Chrome, Edge, Safari* 등이 대표적인 웹 브라우저다.  

`웹 브라우저`란 웹에 접속하기 위해 사용하는 **소프트웨어**다. **웹 브라우저**는 **HTTP**를 통해 인터넷 상에서 통신을 하며 서버로부터 전달받은 다영한 웹 리소스들을 가공해 사용자가 웹을 사용할 수 있도록 도와주는 소프트웨어다. 따라서 사용자는 **HTTP**의 원리와 동작 방식을 몰라도 **웹 브라우저**를 통해 웹의 불편함 없이 이용할 수 있다.


## 📌 Web Resource
`웹 리소스`는 웹에서 사용하는 콘텐츠를 의미한다.  
웹 브라우저의 주소창에 http://day0522.github.io/index.html 를 입력하면 *day0522.github.io*에 존재하는 */index.html* 리소스에 대해 요청을 수행하는 것이다.  

웹 페이지를 구성하는 대표적인 웹 리로스들은 다음과 같다.
- **HTML** 
  - 웹 문서의 뼈대를 구축하기 위한 마크업 언어
  - 정해진 태그와 속성을 지정하여 문서를 구성
- **CSS**
  - HTML이 표시되는 방법을 정의하는 스타일 시트 언어
  - 이미지, 태그, 글자 등 다양한 웹 리소스의 출력에 대한 스타일 설정    

    *HTML과 CSS는 화면에 뼈대를 그리는 것임*

- **JS(JavaScript)**
  - 페이지 내에서의 행위들을 설정할 수 있음
- **Etc** : 문서, 이미지, 동영상, 폰트 등

## 📌 URI(URL)
> 쉽게 말하자면 URI는 주소창에 출력되는 주소 전체이다.  

- `URI` : *Uniform Resource Identifier*의 약자로 리소스를 식별하기 위한 식별자
- `URL` : *Uniform Resource Locator*의 약자로 리소스의 위치를 식별하기 위한 URI의 하위 개념  
웹 사이트의 주소를 이용해 접근한 것은 URL이자 URI를 이용한 것이다.

## 📌 URI 구성 요소
![image](https://kr.object.ncloudstorage.com/dreamhack-content/page/c974f9087eddea560f7ff225c5d6e35a0cfdfd1a1df14c284271ff321846e497.png) 
  - **Scheme** : 웹 서버에 접속할 때 어떤 체계(프로토콜)를 이용할지에 대한 정보를 담고 있다.
  - **Authority** : Host와 Port로 구성
    - **Host(Domain)** : 접속할 웹 서버의 호스트(서버 주소)에 대한 정보를 가지고 있음
    - **Port**
      - 접속할 웹 서버의 포트에 대한 정보를 가지고 있음
      - 포트가 명시되어 있지 않으면 각 프로토콜에 해당하는 **표준 포트(HTTP:80, HTTPS:443)**로 해석함
  - **Path** : 접속할 웹 서버의 경로에 대한 정보를 가지고 있으며 / 문자로 구분됨
  - **Query** : 웹 서버에 전달하는 파라미터(추가적인 정보)로 ? 문자 뒤에 붙음
  - **Fragment**
    - 메인 리소스 내에 존재하는 서브 리소스에 접근할 때 이를 식별하기 위한 정보를 담고 있으며 # 문자 뒤에 붙음
    - 해당 페이지 내 북마크 역할
    - 어떤 링크를 눌렀을 때 페이지 내의 특정 위치로 이동시킴(서버로 전송시켜주는 데이터는 아님)

## 📌 Encoding
`Encoding(인코딩)`은 문자 또는 기호 등의 정보, 형태를 표준화, 보안 등의 목적으로 다른 형태나 형식으로 변환하는 처리를 말한다. 이렇게 변환된 형태를 원래 형태로 변경하는 것을 `Decoding(디코딩)`이라 한다.
- Encoding(인코딩) : 알고리즘이 모두 공개되어 있으며 키와 같은 요소가 포함되어 있지 않아서 모두가 원래의 정보로 복원이 가능함
- Encryption(인크립션)
  - 양방향 암호 알고리즘
  - 일치한 알고리즘과 유효한 키를 가지고 있다면 원래의 정보로 복원이 가능  

웹에서 사용하는 대표적인 인코딩으로 **URL**과 **HTML Entity**가 있다.
- **URL Encoding(percent encoding)**
  - URI 구조내에서 예약어(구분자)로 사용되는 문자들을 전송하고자 할 때 사용
  - 인코딩 방식
    - 입력된 문자를 Ascii테이블에서 매칭되는 Hex 값 앞에 `%`문자를 붙이면 됨
    > ?는 %3F, #은 %23, &는 %26으로 나타낼 수 있다.  

        |문자|URL 인코딩|
        |:-----:|:-------:|
        |?|%3F|
        |#|%23|
        |&|%26|
        |=|%3D|

- **HTML entity Encoding**
  - HTML 문서에서 사용하는 문자열이 HTML 태그로 인식하지 않도록 하기 위해 사용
  - 인코딩 방식
    - 입력된 문자를 Ascii테이블에서 매칭되는 Hex 값 앞에 `&#x`를 붙이면 됨
    - 주요한 문자들에 대해서는 지정되어 있는 Entity name을 사용하면 됨  

      |문자|Entity name encoding|Entity number encoding|
      |:------:|:---------:|:---------:|
      |&|%amp;|`&#x26;`|
      |<|%lt;|`&#x3C;`|
      |>|%gt;|`&#x3E;`|

## 📌 HTTP
> https://day0522.github.io/ URI는 HTTPS 방식으로 day0522.github.io 서버와 통신하는 것이다.  

`HTTP` 또는 `HTTPS는` URI의 구성 요소 중 **Scheme(Protocol**)에 해당한다. HTTP와 HTTPS의 핵심 구조 및 동작 원리는 동일하므로 HTTP로 통칭되기도 한다.

- **Protocol(프로토콜)**
  - 컴퓨터 내부 혹은 컴퓨터 사이에서 어떻게 데이터를 교환할지를 정의하는 규칙 체계
  - **HyperText Transfer Protocol(HTTP)**, **HyperText Transfer Protocol Secure Socket Layer(HTTPS)**은 웹에서 이루어지는 통신을 정의한 프로토콜이다.
  -  TCP 혹은 TLS(암호화된 TCP)를 사용해 통신하고 기본 포트로 80(HTTP), 443(HTTPS) 포트를 사용한다. 이때 포트 번호는 서버의 설정을 통해 변경 가능하다.

HTTP는 사용자가 서버에 요청을 하는 `Request`와 사용자의 요청에 대한 서버의 응답인 `Response`로 나누어진다.  

## 📌 HTTP Request
`HTTP Request`는 서버에 대한 요청을 의미한다.  
HTTP Request의 구조 중 가장 첫번째 줄에는 `Method`, `Path`, `Version`으로 구성된다. 두 번째 줄부터는 `Header` 부분이며, 마지막에는 `Body`로 구성된다.

```HTTP
GET /index.html HTTP/1.1
Host: day0522.github.io
Connection: keep-alive
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.88 Safari/537.36
```

### **HTTP Request 구성요소**
- **Method**: 서버에 요청 시 수행하고자 하는 동작을 나타냄
  > 서버에서 설정하는 방식, 웹 어플리케이션의 처리에 따라 수행하는 방식이 다를 수 있음   
  - OPTIONS: 요청하는 리소스가 허용되는 메소드 목록을 반환  
  - GET: 리소스를 요청  
    >ex) 게시물/프로필 보기, 이미지 등*
  - HEAD: GET 메소드와 동일하지만, Response의 Body 부분은 받지 않고, Header만 받음
    >ex) 서버의 상태 확인 등
  - POST: 특정 리소스 생성 및 데이터 추가를 위해 값을 제출할 때 사용
    >ex) 게시물/프로필 생성 등
  - PUT: 특정 리소스의 내용을 보낸 값으로 설정
    >ex) 생성/업데이트 등 
  - PATCH: 특정 리소스의 내용 중 보낸 값의 key만 변경
    >ex) 게시글 업데이트 등
  - DELETE: 특정 리소스를 삭제
    >ex) 게시물 삭제 등
  - TRACE: 요청받은 값을 Response의 Body로 다시 클라이언트에게 되돌려줌  

- **Path**: 사용자가 서버에 요청하는 웹 리소스의 경로

- **Version**: HTTP의 버전

- **Header**
  - `이름: 값` 형태로 이루어짐
  - 서버에 추가 정보를 전달하는 데이터 부분
  - 사용자와 서버가 상호작용하기 위한 정보를 담는 부분
    *ex) 사용자 데이터의 처리 방식 및 형식에 대한 정보, 서버에서 사용자를 식별하기 위한 쿠기 정보 등*
  
  **주요 Header**
  - Host: 데이터를 보내는 서버의 주소
  - Cookie: 사용자를 식별하기 위해 사용하는 정보
  - User-Agent: 사용자가 사용하는 프로그램의 정보
  - Referer: 페이지 이동 시 이전 URI의 정보
  - Content-Type
    - 사용자가 전달하는 데이터의 처리 방식과 형식
    - 사용자와 서버 간의 데이터 처리 방식이 일치돼야 정상적인 데이터 통신이 이루어짐

- **Body**: 사용자가 입력한 데이터를 서버에 전달할 때 데이터를 담는 부분

## 📌 HTTP Response
`HTTP Response`는 사용자의 요청에 대한 서버의 응답을 의미한다.  
HTTP Request의 구조 중 가장 첫번째 줄에는 `Version`, `Status code`로 구성된다. 두 번째 줄부터는 `Header` 부분이며, 마지막에는 `Body`로 구성된다.
```HTTP
HTTP/1.1 200 OK
Server: Apache/2.4.29 (Ubuntu)
Content-Length: 61
Connection: Keep-Alive
Content-Type: text/html

<!doctype html>
<html>
<head>
</head>
<body>
</body>
</html>
```  

### **HTTP Response 구성요소**
- **Version**: HTTP의 버전  

- **Status Code**: 사용자의 요청에 대한 서버의 처리 결과
  - 주요 Status Code에 대해 자세히 알고 싶다면 [여기](https://day0522.github.io/posts/Introduction-of-Web/) 게시글을 확인하자.
- **Header**: 사용자와 상호작용하기 위한 데이터를 담는 부분
  > ex) 사용자(웹 브라우저)에서 서버의 응답 데이터를 처리하는 방식 및 형식에 대한 정보, 서버에서 사용자를 식별하기 위한 쿠키 발급 정보 등
  - Content-Type: 서버의 응답 데이터를 웹 브라우저에서 처리할 방식과 형식
  - Content-Length: 서버가 사용자에게 응답해주는 데이터의 길이
  - Server: 서버가 사용하는 소프트웨어의 정보
  - Allow: 허용되는 Method 목록을 사용자에게 알려줄 때 사용
  - LocationL 300번 영역의 응답 코드 사용 시 변경된 웹 리소스의 주소
  - Set-Cookie
    - 사용자에게 쿠키를 발급할 때 사용
    - 해당 헤더를 받은 웹 브라우저는 해당 쿠키를 저장
- **Body**: 서버가 사용자에게 응답하는 데이터를 담는 부분