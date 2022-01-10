# Servlet이란?

웹 기반의 요청에 대한 동적인 처리가 가능한 Server Side에서 돌아가는 Java Program 이다.
Java 코드 안에 HTML 코드가 들어간다.



# 과정

Client(get / post)->request->WAS->DB->WAS->response->Client



# Container

JVM이 있는 환경



# life cycle

> Servlet 제어 관리

1. init : 생성자 역할(connect)

2. service- doGet, doPost

3. destroy : connect 끊음



# web.xml 

하나의 웹 application(service) 설정 정보

XML : 태그를 정의 할 수 있는 언어

장점 : 파일형태여서 또다른server 필요 ㄴㄴ



# Query String

하나의 서블릿에 여러개의 작업을 처리가능

형식 : ?~
