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



