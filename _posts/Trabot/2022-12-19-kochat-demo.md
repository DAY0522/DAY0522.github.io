---
title: "[Trabot] 오픈소스 딥러닝 챗봇 Kochat demo 실행 에러 해결"
excerpt: "한국어를 지원하는 오픈소스 딥러닝 챗봇 프레임워크인 Kochat을 실행할 때 발생하는 에러를 해결해보자자."

writer: Dayeong Kim
categories:
  - Trabot
tags:
  - [오픈소스, opensource, 딥러닝, 챗봇, 프레임워크, kochat, demo, 한국어]

toc: true
toc_sticky: true

date: 2022-12-19
---

지난 게시글에서는 Kochat을 활용한 프로젝트인 Trabot에 대해서 설명했다.

Trabot 프로젝트의 레거시 코드를 수정하기 위해, 다시 Kochat을 실행하기 위한 준비를 해야 한다.

과거에도, 현재에도 Kochat 환경설정을 하는데 매우 애를 썼기 때문에 미래에서라도 이를 방지하고자 demo 실행 과정에 대한 기록을 하고자 한다.

[Kochat demo 실행](https://willbesoon.tistory.com/250) 사이트에 설명이 잘 돼있으니 전반적인 내용은 해당 사이트를 참고하도록 하자. 필자는 위 사이트대로 진행하면서 문제가 발생한 부분만 추가적으로 기록할 것이다.

# 🤖 Kochat 환경설정

먼저 [Kochat github](https://github.com/hyunwoongko/kochat)에 들어가 repo를 clone한다.

clone이 끝난 후에 해당 폴의 하위 폴더인 demo에 들어가면 `application.py` 파일이 있는데, 이게 Kochat을 사용하기 위한 서버 실행 코드이다.

우선 Kochat 프로젝트를 사용하기 위한 가상환경을 생성하자.

참고로 현재 필자의 개발환경은 다음과 같다.

- pycharm: 2022.2.4
- pip: 22.3.1
- JDK: 19.0.1
- Anaconda3: 2022.10(Python 3.9.13 64-bit)
- \_jpype.cp37-win_amd64.pyd
- venv python: 3.7

# 1️⃣ 가상환경 설정

Anaconda가 문제인 건지, Kochat이 문제인 건지 왠지 모를 이유로 Pycharm에서 가상환경 연결이 잘 안 됐다. 이런 경우에는 과감히 VScode 같은 다른 개발 환경으로 넘어가자.

필자는 데스크탑에서는 파이참으로 실행이 됐지만, VScode는 실행되지 않았다... (진짜 왜 그런지 모름)

# 2️⃣ 라이브러리 설치

개발자가 작성해둔 `requirements.txt`에 작성된대로 라이브러리를 설치하고 `application.py`를 실행하면 라이브러리의 버전과 관련한 에러가 발생한다.

따라서 필자는 다음과 같이 `requirements.txt` 파일을 수정했다.

```
matplotlib==3.2.1
pandas==1.0.4
gensim==3.8.3
konlpy==0.5.2
numpy==1.18.5
joblib==0.15.1
scikit-learn==0.23.1
pytorch-crf==0.7.2
requests==2.24.0
flask==1.1.2
jinja2<3.1.0
itsdangerous==2.0.1
werkzeug==2.0.3
tweepy==3.10.0
```

이후 `pip install -r .\requirements.txt`를 다시 하자.

# 3️⃣ java.nio.file.InvailidPathException 에러

이번에 데모 실행하면서 제일 난감했던 에러였다.
위에서 게시한 블로그에도 같은 에러가 있었지만, 똑같이 설정해도 추가로 발생하는 에러이다.

![image](https://github.com/DAY0522/DAY0522.github.io/blob/master/_posts/image/kochat_demo_java_error.png?raw=true){: .align-center}{: width="40%" height="40%"}

해결 방법은 아래와 같이 하면 된다.

먼저 자신의 개발환경 디렉토리로 이동하고 다음 경로에 있는 파일을 찾자.
`\Lib\site-packages\konlpy\jvm.py`

해당 파일에 있는 아래 코드에서 \*를 모두 없애자.

```python
folder_suffix = [
    # JAR
    '{0}',
    # Java sources
    '{0}{1}bin',
    '{0}{1}*',
    # Hannanum
    '{0}{1}jhannanum-0.8.4.jar',
    # Kkma
    '{0}{1}kkma-2.0.jar',
    # Komoran3
    '{0}{1}aho-corasick.jar',
    '{0}{1}shineware-common-1.0.jar',
    '{0}{1}shineware-ds-1.0.jar',
    '{0}{1}komoran-3.0.jar',
    # Twitter (Okt)
    '{0}{1}snakeyaml-1.12.jar',
    '{0}{1}scala-library-2.12.3.jar',
    '{0}{1}open-korean-text-2.1.0.jar',
    '{0}{1}twitter-text-1.14.7.jar',
    '{0}{1}*'
]
```

거의 4시간 정도 싸운 후에 해결한 거 같다...

이 외에도 자바 관련 에러가 굉장히 많았는데 해결 됐음에도 왜 해결됐는지 이유조차 모르겠다.
