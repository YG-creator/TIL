## 0. 작동원리 && 프로그래밍이란?
1. 작동원리

java 소스코드 작성 -> compile -> class 생성 -> 가상머신(eclipse)이 class읽어서 명령 -> 컴퓨터 작동

2. 프로그래밍이란?

프로그램 = 데이터(대상)+프로세스(방법)  /   요구사항을 위해서 어떤 프로세스(수행절차)를 행할것인가 
프로그램 언어란(문법)? - 컴퓨터와의 의사소통 언어 = 기호+키워드+식별자
프로그래밍이란 ? - 컴퓨터에게 작업지시하기 

3. 객체지향 프로그래밍

   실행+data+로직 클래스

## 1. 자료형

1. 자료형
   boolean
   char(2), String
   정수 자료형 : byte, short(2), int(4), long(8).
   실수 자료형 : float(4), double(8)

2. 자료형 변환 - 자료손실 방지
   ( byte / char ) -> short -> int -> long -> float -> double 의 방향으로 가능하다.

   데이터 타입(메모리 사용 크기 순서)- char,short 조심
   타입 변환(자동(작->큰), casting(큰->작))  /  byte,short는 연산하면 int로 확장됨

   자바는 웬만하면 string으로 출력 - 변환이 다 가능함
   데이터타입.parse타입(String) -> 데이터타입    /  주의점 String에 빈칸이 있으면 안됨
   데이터타입.valueOf(정수)  : 정수->데이터타입으로
   
3. 변수명 규칙
   특수문자 ㄴㄴ, 숫자 처음 ㄴㄴ

4. 상수
   final 변수명 : 상수 - 수정 ㄴㄴ

## 2. 변수(데이터)

1. 용도 : 반복, 고정제거- 변수(선언,초기화,사용)
2. 선언-> 초기화 -> 사용
3. 타입 
   1) 기본형 변수 : 한 변수에 값을 1개 가짐
   2)  참조형 변수: 한 변수에 참조한 여러개 값을 가짐

## 3. 연산자

연산자 : +,-,*,/,%
문자열 더하기 = 붙여쓰기
치환연산자 : 연사자 + =
비교연산자 : == : 원시데이터(bool,실수,정수,char) 비교 - 값이 위치하는 곳이 같은가
equals() : 비원시데이터(문자열,배열...) 비교 - 내용이 같은가
final 변수 : 고정 상수
조건부 연산자
Conditions placed in parentheses - ()
NOT - !
AND - &&
OR - ||

## 4. 조건문

1. if-else

2. switch

## 5. 반복문

while - 반복횟수 모를 때

for - 반복횟수 알 때

## 6. 배열

연관된 정보를 그룹핑
String[] a = {~~};
index : []
a.length : 배열 길이
args 배열 : main()메서드에 전달되는 클레스의 메서드 - 입력값

## 7. collection

1. 정의 : 하나의 변수로 열개의 데이터 CRUD

2. 종류(순서,중복)
   Map(순서x, 중복o),-- key(이름)
   Set(순서x, 중복x) --> Iterator
   List(순서o 중복o) --> index(순서)
   <> : 제너릭 : 입력받을 데이터 형식지정
   
3. ArrayList

   선언 : ArrayList<타입> list = new ArrayList<타입>();

   add() : 추가

   get(index) : 인덱스에 해당하는 값 출력
   set() : 변경
   size() : 크기

   remove() : 제거

   indexOf() : 특정 값을 가진 항목의 인덱스 검색

   contains(값) : 값있는지 확인


4. Map

   선언 : HashMap<key데이터타입,value데이터타입> map = new HashMap<key데이터타입,value데이터타입>();

   put(key,value) : 키:값 삽입, 값 수정

   get(key) : key에 해당하는 값 가져오기

   size() : key 갯수

   remove(key) : key와 value 삭제

   key값과 value 가져오기

   ```java
   Set<String> keys = map.keySet();	//순서없는 key
   Iterator<String> iter = keys.iterator(); //key 줄세움
   while(iter.hasNext()) {	//다음이 있으면
   	String key = iter.next(); // key 가져와라
   	Integer value = map.get(key);// 값 가져와라
   	System.out.println(key+":"+value);
   }
   ```

   

## 8. 메소드(프로세스)

1. 정의
    서로 연관된 코드를 모아서 이름을 붙이는 정리 정돈의 도구
    메서드 정의 : return type, name, parameters

  메소드(void = no return)

  메서드 호출 :  .method()
  매개 변수 : 메소드의 입력 값 - 괄호안에 입력
  return : 출력
  메소드를 사용하여 인스턴스 필드의 값을 변경할 수 있습니다.
  범위 : 변수는 생성 된 도메인 내에서만 존재

2. 문자열 method
    length() : 길이
    concat() : 합치기
    indexOf()	: 특정값 인덱스
    charAt()	: 특정 인덱스의 값
    equals() : 같은지 확인
    substring(a,b) : (a 이상, b미만 )인덱스 부분 문자열
    toUpperCase() / toLowerCase() : 대문자/ 소문자 변환

     split() : 나누기
    
    trim() : 빈칸 제거
    
3. 수학 메서드
     min, max
       pow,sqrt
       random()*n+1

4. getter , setter

## 9. 입력과 출력

1. String[] args -  Program Arguments에 작성된 입력 값
2.  앱 실행중 입력
   import java.util.Scanner;
   Scanner sc = new Scanner(System.in);
   int i = sc.nextInt();
   ~
   sc.close();

## 10. 접근제어자

1. public : class 밖에서도 사용가능 - 사용자가 사용하는거 ex) 작동장치
   class 밖에서 함수 사용 -> class이름.함수()
   class 밖에서 변수 사용 -> class이름.변수=~
2. protected : 상속아닌거 불용
3. default : 다른패키지 불용
4. private : class 안에서만 사용가능 - 사용자가 사용 안하거나 밖으로 노출 되면 안되는 거 ex) 비밀번호 

## 11. 객체지향

1. 객체지향

   ​	객체지향- 객체가 존재해야 작동함(속성,메소드)

   ​	객체지향 특징	

   ​		1. 상속 : 상위클래스 거를 사용 

   ​		2. 다형성 : overloading, override(부모 메소드 재정의, 접근제한			을 더 강하게 못함, 반대는됨, 예외처리 불가)

   ​		3. 은닉성 : private

2. 객체(instance) : 존재하는 모든것(물리,추상) 
   (1) 구성 : 필드(속성),메소드(동작)
   (2) class : 객체에 사용할 필드,메소드 정의
   (3) 상호작용 : 속성,동작 공유(비밀, 공개) -> 접근 키워드로함
   (4) 사용하는 이유 :  3R(Responsibility,Reuse,Relation)
   Reuse : instance이름.메소드()  
   Responsibility : 인스턴스화 : class이름(datatype) 객체이름 = new class이름() 사용
   Relation : 집합,사용,상속

3. class
   (1) 구성 :  필드(변수), 생성자, 메소드
   (2) 장점 : 연관된것끼리 묶어놔서 보기 편함

   (3) 종류 : 실행클래스- main 

​                        서비스 클래스 - 나머지

4. instance
   (1) 개념 : class와 구조가 같은 객체
   (2) 사용 : instance화(class에서 static 제거)  -> main 함수 안에 class이름 객체이름 = new class이름(); 작성
   (3) 장점 : class 상태(변수)가 자주 변할 때 사용

1. static
   static - class method -> instance에서 수정하면 class 구조도 바뀜
   no static - instance method -> instance에서 수정하면 instance만 변경  ,  class에서 호출 ㄴㄴ

## 12. 생성자, this

1. 생성자 : 초기에 주입 할 값을 전달 할 때 쓰임
   작성법 : main 함수 안에 class이름 객체이름 = new class이름(값); 작성 ->
              class 안에 public class이름(parameter){변수 = parameter;} -> 변수와 parameter이름이 같을 때 this를 사용(this.변수 = 변수;)
2. this : class가 instance화 되었을 때(no static) instance를 가리키는 특수한 이름
3. overloading : parameter 여러개 설정 가능

## 13. 상속 - 부모 class 거 그대로 사용

1. 형식 : class 상속받는class extends 부모class{~}
2. 쓰임 : 부모 class 기능 추가, 수정(overriding)
3. overloading :  parameter 갯수 증가 - class에 같은 함수를 추가하고 parameter를 추가함
4. super : overriding 하기전 함수를 사용 할 경우(super.함수이름())  / 자식class에서 생성자를 사용할 경우
5. this : class 내 함수값을 사용 할 때 this.함수이름() 사용(this.함수이름

## 14. UI, API

UI(User Interface)
API(Application Programming Interface)란 자바 시스템을 제어하기 위해서 자바에서 제공하는 명령어들
http://docs.oracle.com/javase/ - 참고해서 명령어들 기능을 찾을 수 있음

## 15. abstract

1. 개념 : 상위 클래스는 시그니처만 정의 -> 구체적인 구현은 상속된 하위 클래스에서 오버라이딩 강제 규제
2. 사용 이유: 
   상황에 따라서 동작 방법이 달라지는 메소드는 추상 메소드로 만들어서 하위 클래스에서 구현하도록 하고 
   모든 클래스의 공통분모의 경우에는 상위 클래스에 두어서 코드의 중복, 유지보수의 편의성 등을 꾀할 수 있다.

3. interface
   (1) 개념 : 하위 클래스에 특정한 메소드가 반드시 존재하도록 강제
   (2) 형식
   interface 이름{함수()}
   class A implements 이름{ 함수(){}}
   (3) 용도 : communication miss를 줄일 수 있음 App개발자 -  App 사용자  /  사용자가 기다릴 필요가 없음
   (4) 규칙
   한개의 클래스에 여러개 interface 구현 가능
   interface도 상속이 된다
   interface 맴버는 반드시 public 이어야 한다
   (5) abstract(0이상) vs interface(0)

## 16. 예외 처리

- 형식

  try{예외의 발생이 예상되는 로직}
  catch(예외클래스 인스턴스){예외가 발생했을 때 실행되는 로직}
  finally{예외여부와 관계없이 실행되는 로직}

- 메소드

  e.getMessage() : 요류내용 출력 - 상세 ㄴㄴ
  e.toString() : 어떤 영역에서 예외 발생 출력 - 조금 상세(기본 패키지만)
  e.printStackTrace() : 내부적으로 예외 결과를 출력 - 상세(기본+다른 패키지)

- 예외클래스
  ArrayIndexOutOfBoundsException : index
  ArithmeticException : 연산
  Exception : 모든 예외

## 17. File

1) File

2. 메소드
   생성자 : new File("./폴더/이름.형식")
   .getName()
   .length();
3. class
   File : 사용할 파일
   FileReader : 내용 읽어오기
   BufferedReader : 한줄씩 읽어오기

## 18. Multi Thread

thread : 작은 프로세스
동시성(동시에)과 병렬성(여러가지) 작업
override
스레드 객체 생성 ->start()-> 실행 대기 -> 실행(시간,중요도순) -> 종료
쓰레드는 resume(), suspend(), stop() 은 사용 ㄴㄴ -> 요즘 프레임워크가 알아서 해줌
Thread.sleep(1/1000초); -  try-catch 해줘야됨

## 19. Annotation

Annotation
자동으로 배치프로그램 작성
ex) @Override

***

# 아직 정리 안된거


클래스 : 프로그램의 기본 단위 (객체에 사용할 필드,메소드 정의)
인스턴스 : 프로그램 실행할 때 기본단위
메소드 : 작업지시의 집합
파라미터 :  작동에 영향을 미치며, 외부로부터 투입되는 데이터
매개변수 :  작동에 영향을 미치며, 외부로부터 투입되는 데이터
실인수 :  실제값
가인수 :  값을 받는 곳(변수)
인자 : 작동에 영향을 미치며, 외부로부터 투입되는 데이터
알고리즘 : 작업 순서

식별자 : 구별 할 수 있는 유일한 이름
생성자 : 객체 생성시 작동하는 코드
초기화 : 변수에 최초로 값을 할당하는 과정
참조형 : 하나의 변수에 1개 이상의 값을 저장할 수 있는 데이터 타입
기본형 : 하나의 변수에 값 하나 저장할 수 있는 데이터 타입
키워드 : 컴퓨터 프로그래밍으로 고정된 예약어
연산자 : 물리학과 수학에서 어떤 함수에 작용해 그 함수를 다른 함수로 변형시키는 함수

인덱스 : 데이터의 주소
요소 : 배열을 구성하는 각각의 값
배열 : 여러개의 값(같은 타입)을 저장 할 수 있는 데이터 구조

​	

2. 타입변환과 다향성
    같은 타입이지만 결과가 다름
    부모클래스 변수 = 자식클래스타입변수 -> 부모타입만 변수에들어감
    자식클래스 변수 = (자식클래스) 부모클래스타입 -> 강제 타입변환(casting)
    instanceof : 부모자식 확인

  

