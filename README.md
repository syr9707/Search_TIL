# 탐색 알고리즘 (완전탐색, BFS, DFS)

## * DFS (Depth-First-Search, 깊이 우선 탐색)

> 두 가지 방법으로 풀 수 있음

1) 스택을 이용함
2) 재귀함수를 이용함, 재귀함수의 코드가 훨씬 짧음
3) 모든 경우의 수를 탐색하고자 하는 미로 문제 같은 경우 적합 -> 미로 : 최단 경로 X, 탈출 경로 O

* 재귀적으로 동작 (재귀, 스택)
* 그래프 탐색의 경우, 어떤 노드를 방문했었는지 여부를 반드시 검사 (검사하지 않으면 무한루프)
* 모든 노드를 방문하고자 할 때 사용
* BFS 보다 간단, BFS에 비해 검색 속도 느림
* 모든 노드 방문하고자 할 때 사용

```java
// dfs, 재귀, 인접 행렬, i 정점부터 시작
public static void dfs(int i) {
    visit[i] = true;
    for(int j = 1; j < n + 1; j++) {
        if(map[i][j] == 1 && visit[j] == false) {
            dfs(j);
        }
    }
}
```


## * BFS (Breath-First-Search, 너비 우선 탐색)

> Queue를 사용해 문제를 해결

1. 두 지점 사이의 최단 경로를 찾는 문제에 적합함
2. FIFO (First-In-First-Out) 원칙

* 재귀적으로 동작하지 않음
* 그래프 탐색의 경우, 어떤 노드를 방문했었는지 여부를 반드시 검사 (검사하지 않으면 무한루프)
* 큐(FIFO) 사용 : 방문한 노드들을 차례로 저장하고 꺼낼 수 있음
* 넓게 탐색
* 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때 사용

```java
// bfs, 큐 사용, 인접행렬, i 정점부터 시작
public static void bfs(int i) {
    Queue<Integer> q = new LinkedList<>();
    q.offer(i);
    visit[i] = true;
    while(!q.isEmpty()) {
        int temp = q.poll();
        for(int j = 0; j < n + 1; j++) {
            if(map[temp][j] == 1 && visit[j] == false) {
                q.offer(j);
                visit[j] = true;
            }
        }
    }
}
```