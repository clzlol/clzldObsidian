---
kind: language
status: To Do
urgent: false
---
***

여기에서는 Java로 입력을 받는 방법을 정리해볼 거다. 크게 BufferedReader와 Scanner가 있다. 간략하게 요약하면 다음과 같다.
![[BufferedReader vs Scanner.png]]

## Scanner

토큰 단위(스페이스바, 엔터, 탭 등)를 입력값의 경계로 인식해 데이터를 쉽게 입력 받는다. 데이터 타입이 입력 받는 시점에서 결정되어 타입 변환이 필요 없다.
- 주요 메서드 (각 메서드의 X 자리에는 타입을 적는다.)
	- `nextX()`: X 타입의 데이터를 입력 받는다.
			-String 타입을 받을 때는 nextString()이 아니라 next()와 nextLine()을 쓴다. next()는 띄어쓰기를 기준으로, nextLine()은 Enter를 기준으로 입력 받는다.
	- `hasNextX()`: boolean을 리턴 하며 입력 받은 값과 X의 타입이 같으면 true를 반환한다.
	- `findInX(A)`: 입력 받은 값에서 A가 포함된 내용을 찾아 리턴 한다. 없으면 null 반환한다.

*Example*
```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
    
        Scanner s = new Scanner(System.in);
        
        long a = s.nextLong();
        int b = s.nextInt();
        String str = s.nextLine();
        String str2 = s.next();
    }
}
```

## BufferedReader

