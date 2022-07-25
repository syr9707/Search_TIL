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



