# Stack (LIFO : Last - In - First - Out)

> 입력 : A -> B -> C 
>
> 출력 : C -> B -> A

*Tip. 스택과 큐 모두 Java 기준, 기본적으로 라이브러리 제공*

> 원소 삽입 : push()
>
> 원소 조회 : peek()
>
> 원소 뺴냄 : pop()

```java
import java.util.*;


    Stack<Integer> stack = new Stack<>(); // 스택 객체 생성

    stack.push(1); // push : 스택에 1 삽입
    stack.push(9); // push : 스택에 9 삽입
    stack.push(13); // push : 스택에 13 삽입
    System.out.println("Stack : " + stack);
    // 출력 - Stack : [1, 9, 13] 

    int peek = stack.peek(); // peek : 다음에 빼낼(맨 뒤) 원소 '조회'
    System.out.println("peek : " + peek);
    // 출력 - peek : 13

    System.out.println("Stack : " + stack);
    // 출력 - Stack : [1, 9, 13] 

    int pop = stack.pop(); // pop : 맨 뒤의 원소 '빼냄'
    System.out.println("pop : " + pop);
    // 출력 - pop : 13

    System.out.println("Stack : " + stack);
    // 출력 - Stack : [1, 9]

    pop = stack.pop(); // pop : 맨 뒤의 원소 '빼냄'
    System.out.println("pop : " + pop);
    // 출력 - pop : 9

    System.out.println("Stack : " + stack);
    // 출력 - Stack : [1]
```

### ● 좌표는 설정하기 나름 : x, y 잘 설정하기
```java
// 백준 1012 배추 : DFS 
public static void dfs(int startX, int startY) {
		check[startX][startY] = true;
		
		int[] X = {0, 0, -1, 1};
		int[] Y = {-1, 1, 0, 0};
		
		for(int i = 0; i < 4; i++) {
			int x = startX + X[i];
			int y = startY + Y[i];
			
			if(x < 0 || x >= M || y < 0 || y >= N) {
				continue;
			}
			
			if(arr[x][y] == 1 && !check[x][y]) {
				dfs(x, y);
			}
		}
	}
```

### ● 대각선 좌표 : 위 아래가 한 쌍으로 좌표에 더해지는 것 
```java
public static void dfs(int startY, int startX) {
		check[startY][startX] = true;
		
		// 위아래를 한 쌍이라고 생각하면 쉬움 
		// 아래, 위, 왼, 오, 오위, 오아래, 왼위, 왼아래 
		int[] X = {0, 0, -1, 1, 1, 1, -1, -1};
		int[] Y = {-1, 1, 0, 0, 1, -1, 1, -1};
		
		for(int i = 0; i < 8; i++) {
			int x = startX + X[i];
			int y = startY + Y[i];
			
			if(x < 0 || x >= w || y < 0 || y >= h) {
				continue;
			}
			
			if(arr[y][x] == 1 && check[y][x] == false) {
				dfs(y, x);
			}
		}
		
	}
```