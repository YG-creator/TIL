# Java

*****

### 💻 기초 명령어 설명 💻

***

##### 💡 기본구성 💡

```java
// 패키지명
package mc.sn.Example;

// 메인 클래스
public class Test {

    // 메인 메소드
	public static void main(String[] args) {
        
    }
}
```

****

##### 💡 출력 💡

```java
package mc.sn.Example;

public class Test {

	public static void main(String[] args) {
        // 출력 명령
        System.out.println("Hello World!");			// 1번
        System.out.print("Hello World!");			// 2번
        System.out.println();					   // 3번
        
    }
}
```

1번 라인 출력 (✔은 커서 위치) : **출력하고 줄바꿈**

```
Hello World!
✔
```

2번 라인 출력(✔은 커서 위치) : **출력하고 줄바꿈 안함**

```java
Hello World!✔
```

3번 라인 출력(✔은 커서 위치) : **출력없이 줄바꿈**

```java

✔
```

*****

💡 입력 💡

```java 
package mc.sn.Example;

// 입력 메소드 Scanner 사용을 위한 import를 해줘야함
import java.util.Scanner;

public class Test {

	public static void main(String[] args) {
        int A;		// 정수형 변수
        float B;	// 실수형 변수
       	String C;	// 문자열 변수
        
        // 입력 메소드 인스턴스화
        Scanner sc = new Scanner();
        // 입력 명령
        A = sc.nextInt();
        B = sc.nextFloat();
        C = sc.nextLine();      
    }
}
```

