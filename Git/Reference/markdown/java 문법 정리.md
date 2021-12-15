# 	java 문법 정리

##   주석

```java
주석 사용시 //를사용하여 주석을 입력할수있다
    
```

## 변수

- 하나의 값을 저장할 수 있는 메모리 공간
- 첫 번쨰 글언된 블록 내에서만 사용이가능





**변수는 초기화가 되어야 읽을수가 있고 초기화되지 않는 변수는 읽을수가없다**

- #### 잘못된 ex )

```java
int value; //변수 value 선언 (초기화 안 됨)
int result = value + 10 //변수 value 값을 읽고 10을 더한 결과값을 변수 result에 저장
   
```

- #### 옳바른 ex)

  ```java
  int value = 30; //변수 value가 30으로 초기화됨
  int result = value + 10; //변수 value 값을 읽고 10을더한 결과값(40)을 변수 result 에 저장
  ```

  

### 

## 변수선언

```java
int x = 1; //변수 x를 선언하고 1을 저장
int y = 2; //변수 y를 선언하고 2를 저장
int result = x + y; //변수 result를 선언하고 변수 x와 y를 더한 값을 저장
System.out.pirntln(result); //콘솔에 출력하는 메소드 호출 
```



## 데이터 타입

### 정수 

```java
byte < char <= short < int < long  //크기별
```

### 실수

```java
float < double //크기별
```

### 논리

```java
boolean(){} //논리 레터럴에는 true 와 false 만 사용가능 
```

