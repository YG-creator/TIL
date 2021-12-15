11 / 5

1. maven(라이브러리 관리) 프로젝트

   라이브러리 관리 - pom.xml 변경

   경로 설정 - pom.xml(artifactId, name), server.xml(context의 path)

   

2. 버전충돌 error

   mysql에 맞게 connector 사용

   mysql5.1 -> com.mysql.jdbc.Driver      

   mysql8.0 -> com.mysql.cj.jdbc.Driver

   

3. 서버 중복 error

   netstat -ano | findstr 9090
   taskkill /F /pid 108811



11/10

1. ajax + spring

   pom.xml - springframewor version update

   controller - @Responsebody, response.getWriter().print(값)

   ajax - data,type,dataType,async,url,success,error,complete

   ​			window.location.href = '/login/success'; 페이지이동

2. 프로젝트(문제점 해결)

   요구사항- 문제점 찾아라



12/8

1. 자동병원 찾기 (위치,과,시간)

   1. 총과정

      도로명, 과, 사용시간 입력(jsp) -> 네이버 -> 위도, 경도 -> open api -> 병원코드(hpid) -> open api -> 병원 상세 정보 -> 과, 진료시간 데이터 가져오기 -> 입력한거로 분별 -> 가능한 병원만 volist에 담기 -> 병원리스트(jsp) 에 전달

   2. 한거

      도로명, 과, 사용시간 입력(jsp) -> naver -> 위도, 경도 -> open api -> 병원코드(hpid) -> open api -> 병원 상세 정보 -> 과, 진료시간 데이터 가져오기

   3. 막힌거(입력한거로 분별)

      사용시간(1시간은 60분 진법,  but 출력된 시간은 10진법)

      점심시간 따로 출력 안됨



2. 휴원 게시판
   1. jsp(병원이름, 날짜+시간 입력)
   2. db(휴원_id, 작성자 id, 시작 날짜 시간, 끝 날짜 시간, 병원이름, 병원위치)

​		  3.  해야할거 :  jsp, db 연결 -> CRUD



12/ 11

픽쳐스크린 : window+shift + s

팀프로젝트 ppt 작성(사용자 needs, 사용기술, 기능, 해야할거)
