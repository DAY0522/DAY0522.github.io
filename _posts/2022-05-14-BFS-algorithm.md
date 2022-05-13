---
title: "[Algorithm] BFS(Breadth-First Search)"
excerpt: "BFS에 대해 알아보자."

writer: Dayeong Kim
categories:
  - Algorithm
tags:
  - [Algorithm, BFS, 알고리즘, 그래프, 너비우선탐색]

toc: true
toc_sticky: true

date: 2022-05-14
last_modified_at: 2022-05-14
---

# 1. BFS란?

![BFS](https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif){: width="50%" height="50%"}

- `BFS`란 루트 노드(Node)에서 시작하여 인접한 노드를 방문할 때 **너비를 우선**으로 방문하는 알고리즘이다.
- 시작 정점으로부터 가까운 정점을 먼저 방문하고 멀리 떨어져 있는 정점을 나중에 방문하는 순회 방법이다. 이때 한 번 방문한 정점은 다시 방문하지 않는다.
- 노드 사이의 최단 경로를 구하고자 할 때, 혹은 임의의 경로를 찾고자 할 때 BFS를 이용한다.

# 2. BFS를 코드로 구현하려면?

1️⃣ 시작하는 정점을 큐에 삽입하여 방문했다는 표시를 남긴다.  
2️⃣ 큐의 제일 앞에 있는 원소를 삭제한 후, 해당 원소에 연결돼 있으면서 아직 방문하지 않은 정점을 큐에 삽입한다.  
3️⃣ 큐가 비어있을 때까지 2️⃣를 반복한다.

이때 모든 정점(Node)을 한 번, 모든 간선(Edge)을 두 번씩 방문하므로 시간복잡도는 정점이 N개일 때 O(|V|+|E|)이다.

해당 과정을 거치면 [그래프](https://day0522.github.io/posts/graph/)에 연결된 모든 정점을 단계별로 방문할 수 있다.

## 💡 기본 예제 코드(Python)

- graph는 각 인덱스 원소에 대한 인접 원소
- visited는 각 원소의 방문 여부를 저장하는 리스트(방문 시 True, 미방문 시 False)

```python
# 큐 구현을 위한 deque 라이브러리 활용
from collections import deque

# BFS 함수 정의
def bfs(graph, start, visited):
    queue = deque([start])
    # 시작 노드를 방문 처리
    visited[start] = True

    # 큐가 완전히 빌 때까지 반복
    while queue:
        # 큐에서 원소 하나를 pop
        v = queue.popleft()
        print(v, end=' ')
        # pop한 원소와 연결된, 아직 방문하지 않은 원소들을 큐에 삽입
        for i in graph[v]:
            if not visited[i]:
                queue.append(i)
                visited[i] = True

# 각 노드가 연결된 정보를 2차원 리스트로 표현
graph=[
    [], # 0번 노드 비우기
    [2, 3, 8], # 1번 노드와 연결된 2, 3, 8 노드
    [1, 7],
    [1, 4, 5],
    [3, 5],
    [3, 4],
    [7],
    [2, 6, 8],
    [1, 7]
]

# 방문 정보 저장할 리스트
visited = [False]*(8+1) # (총 노드의 개수 + 인덱스 0 저장) 크기로 선언

# bfs 실행
bfs(graph, 1, visited)
```

---

BFS 이미지 출처: [wikipedia](https://ko.wikipedia.org/wiki/%EB%84%88%EB%B9%84_%EC%9A%B0%EC%84%A0_%ED%83%90%EC%83%89)
