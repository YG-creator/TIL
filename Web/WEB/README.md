# 웹

## 	개념

​		웹 : 요청과 응답 과정으로 resource를 주고 받는 촘촘하게 연결된 네트워크

​		HTTP : 통신 프로토콜 통합 = 웹표준화(웹브라우저가 달라도 ㄱㅊ)

​		URL : Resource의 위치를 규정 = PIN번호 : PORTT번호 / 경로

## 	3 tier programming 

​		Web lient(View) + AWS(Controller) + DB(Model)

​		Web Client : 서비스 제공 요청 및 받음,Request, 언어(html,css,javascript)-> jsp파일

​		Web Applicaiont Server(WAS) : 서비스 제공 및 로직처리 ,  Response, 언어(Java) -> Servlet + Tomcat

​		DB : 데이터 관리



# URL

>  http + 도메이네임 + 페이지 + 쿼리스트링

http : html(이미지,텍스트,동영상) 데이터 전달

도메인 네임

페이지 : 데이터 전달, 로직처리

쿼리 스트링 : ?, &



# WAS 환경설정

1. WAS(Tomcat) 설정

   https://tomcat.apache.org 에서 Tomcat 다운로드

   EE에서 server 클릭-> version에 맞는 tomcat 선택-> tomcat 위치 설정

2. 하단Servers -> Add and Remove : html 서버에 배포

3. 주의사항

   이미사용중인 port 사용시 -> 오류 -> 하단 Servers에서 서버 더블클릭 -> port 번호 바꾸기로 해결

4. UTF-8 설정 : window -> preferences->Web->HTML,CSS,Javascipt UTF-8로 변경

   

# 데이터 주고받기

내장 객체(request, response)로 주고 받음
