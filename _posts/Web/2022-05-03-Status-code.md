---
title: "[Web] Status code"
excerpt: "Status Code에 주로 사용되는 code를 알아보자."

writer: Dayeong Kim
categories:
  - Web
tags:
  - [Web, http, https, responce, Status Code]

toc: true
toc_sticky: true

date: 2022-05-03
last_modified_at: 2022-05-03
---

`HTTP Response`의 첫번째 줄은 `Version`과 `Status code`로 구성돼있다. 이 글에서는 Status code 중 주로 사용되는 code에 대해 알아보고자 한다.

# 1. Status code

`Status code`란 사용자의 요청에 대한 서버의 처리 결과를 나타낸다.

# 2. 주요 Status code

## 📌 **200번 영역**

사용자의 요청에 대한 서버의 처리가 성공하였음을 나타낸다.

- 200 OK
- 201 Created

## 📌 **300번 영역**

사용자가 요청한 리소스가 다른 경로로 변경된 경우를 나타내는 영역이다.  
웹 브라우저에서 300번 영역의 응답 상태 코드가 반환되면, Response Header에 포함되어 있는 Location 헤더의 값으로 리다이렉션 한다.

- 301 Moved Permanently
- 302 Found

## 📌 **400번 영역**

사용자가 서버에 요청하는 구조 또는 데이터가 잘못되었음을 나타내는 영역이다.

- 400 Bad Request
  - 사용자가 전달한 데이터 또는 구조의 잘못된 문법으로 인해 서버가 요청을 이해할 수 없음\
- 403 Forbidden
  - 사용자가 해당 웹 리소스에 접근할 권리를 가지고 있지 않음
- 404 Not Found
  - 사용자가 요청한 웹 리소스의 경로에 응답할 데이터가 없음
- 405 Method Not Allowed
  - 사용자가 요청한 Method가 서버에서는 하용하지 않는 Method임

## 📌 **500번 영역**

서버의 에러와 관련된 영역

- 500 Internal Server Error
  - 서버의 에러가 발생했음을 나타냄
- 503 Service Unavailable
  - 서버의 사용자가 요청을 처리할 준비가 되지 않았음
