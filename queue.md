# Queue (FIFO : First - In - First - Out)

> 입력 : A -> B -> C
>
> 출력 : A -> B -> C

*Tip. 큐 : LinkedList를 이용하여 구현되어 있음*

> 원소 삽입 : offer(), add()
>
> 빼낼 원소 조회 : peek()
>
> 원소 뺴냄 : poll(), remove()

|  | 예외 발생 | 값 리턴 |
| --- | --- | --- |
| 추가 | add | offer |
| 삭제 | remove | poll |
| 검사 | element | peek |


```java
import java.util.*;


	Queue<Integer> queue = new LinkedList<>(); // 큐 객체 생성
		
	queue.offer(10); // offer : 큐에 10 삽입
	queue.offer(5); // offer : 큐에 5 삽입
	System.out.println("Queue : " + queue);
	// 출력 - Queue : [10, 5]
		
	queue.add(25); // add : 큐에 25 삽입
	queue.add(99); // add : 큐에 99 삽입
	System.out.println("Queue : " + queue);
	// 출력 - Queue : [10, 5, 25, 99]
		
	int peek = queue.peek(); // peek : 다음에 빼낼(맨 앞) 원소 '조회'
	System.out.println("peek : " + peek);
	// 출력 - peek : 10

	System.out.println("Queue : " + queue);
	// 출력 - Queue : [10, 5, 25, 99]
		
	int poll = queue.poll(); // poll : 맨 앞의 원소 '빼냄'
	System.out.println("poll : " + poll);
	// 출력 - poll : 10
		
	System.out.println("Queue : " + queue);
	// 출력 - Queue : [5, 25, 99]
		
	int remove = queue.remove(); // remove : 맨 앞의 원소 '빼냄'
	System.out.println("remove : " + remove);
	// 출력 - remove : 5
		
	System.out.println("Queue : " + queue);
	// 출력 - Queue : [25, 99]
```

### ● 좌표는 설정하기 나름 : x, y 잘 설정하기
```java
// 백준 1012 배추 : BFS 
public static void bfs(int startX, int startY) {
		Queue<int[]> queue = new LinkedList<>();
		// bfs에서 queue의 역할은 다음 탐색할 좌표를 미리 저장해 놓는 것이다. 
		// bfs 1번 실행될 때마다 인접한 곳을 모두 탐색하고 종료되니 bfs 안에 queue를 선언했다. 
		
		queue.add(new int[] {startX, startY}); // x, y 좌표 저장
		
		check[startX][startY] = true; // 시작좌표엔 배추가 있으니 미리 true로 처리해준다. 
		
		// 배추가 상하좌우에 인접하면 이동할 수 있다. 
		// 현재좌표에서 상하좌우 움직이는 좌표를 지정한다. 
		int[] X = {0, 0, -1, 1};
		int[] Y = {-1, 1, 0, 0};
		
		// queue가 비어있으면 더이상 인접한 배추가 없다는 뜻이다. 
		while(!queue.isEmpty()) {
			int[] poll = queue.poll(); // 저장된 queue를 꺼낸다. 
			
			// 상하좌우 4가지 방법이니 for문 4번 반복
			for(int i = 0; i < 4; i++) {
				// 상하좌우 좌표 조정
				int x = poll[0] + X[i];
				int y = poll[1] + Y[i];
				
				// 좌표가 배추밭을 벗어나게되면 다음 좌표를 체크해야 한다. 
				if(x < 0 || x >= M || y < 0 || y >= N) {
					continue;
				}
				
				// 상하좌우 움직인 좌표에 배추가 있고, 체크하지 않은 좌표이면
				if(arr[x][y] == 1 && !check[x][y]) {
					queue.add(new int[] {x, y}); // 좌표를 저장한다.
					check[x][y] = true; // 체크한다.
				}
			}
		}
		
	}
```

