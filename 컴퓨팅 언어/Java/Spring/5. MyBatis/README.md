sql

connection pool

transanction 처리 - all or nothing



Spring MVC - 외부(Container(XML))에서 객체 생성

결과 url 전달 : ModelAndView객체

url 연결 : XML



JDBC - 외부에서 연결 및 전달

CM Connection pool(JDBC Template객체가 만듦) - Datasource 가져오기

VO, DB 접속정보, Datasource, DAO와 연결, DAO와 service연결, source 위치, 요청처리, viewResolver

ORM : sql , 내부에서 처리 후 리턴 -> xml에 모음 -> 전달

sqlMapper : Session(접속~종료) -> read빼고 commit 필요



MyBatis SRM Framework



DI : 

D : Data source를 content에 연결하기 위해서  멤버변수(필수정보(class형,파일위치))에 의존

I : 외부(Container)에서 데이터 객체생성 후 삽입

stmt : 쿼리를 보내는 통로

외부에서 class 주겠다(수정,변경 가능)



ORM : CM 

MyBatis

DAO(object) <-> ORM <-> DB 

영속성, mapping, DB에 넣고 빼기

connection pooling



다형성 : A b = new B()   /   A c = new C()



semi project 11/2~4

환경설정 2일 -> 기획 -> 데이터 전처리(python)

주어진 시간, 인원, 목표

4시간 기획-> 3시간 발표-> 2일 구현

주요부분으로 나누기



connection pool 확인 (mysql, driver, 아이디, 비번)

ORM mapping, Mybatis

Annotation -> DI, RequestMapping, 

XML - url maaping
