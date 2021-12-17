# server 생성

서버이름 설정

인증키 이름 설정 -> 인증키 다운로드

스토리지 (HDD)

서버 사양(compact)

ACG(ncloud-default)



# 관리자 비밀번호 확인

서버 선택 -> 관리자 비밀번호 확인

server 생성 할 때 다운로드 받은 인증키 파일 업로드 -> 비밀번호 나옴



# 포스트 포워딩

사용할 포트 입력 -> 작성



# PUTTY

컴퓨터의 IP 번호와 포워드한 PORT 번호 입력

 -> ncloud save -> open -> id입력 -> pwd입력 -> 연결됨

IP : 210.89.188.147
관리자 이름 : root
비밀번호 : J4ytnM87LPu
공인 IP : 49.50.160.48



# unix 명령어

| cd                     | 해당 경로로 이동하기                  |
| ---------------------- | ------------------------------------- |
| ls                     | 목록                                  |
| Cntrl C                | 해당 명령어에서 나오기                |
| cat                    | 파일 보기                             |
| vi                     | 파일 수정하기                         |
| a                      | 입력모드                              |
| esc                    | 명령어 모드                           |
| $                      | 파일의 맨 끝 줄로 이동                |
| x                      | 명령어 모드에서 해당 커서 글자 지우기 |
| i                      | 명령어 모드에서 해당커서에서 입력하기 |
| dd                     | 해당커서에 있는 글 지우기             |
| yy                     | 해당커서에 있는 글 복사               |
| p                      | 하당커서에 붙여넣기                   |
| : wq                   | 수정한거 저장하기                     |
| service mysql status   | mysql server 연결상태 확인            |
| service mysql start:   | mysql server 연결                     |
| service mysql stop:    | mysql server 중지                     |
| service mysql restart: | mysql server 재시작                   |

mysql -uroot : mysql 사용

alter user 'root'@'localhost' identified by '비밀번호' : user 비밀번호 변경

create user '아이디'@'%' identified by '비밀번호'; : 사용자 추가

grant all privileages on *.* to '사용자'@'%'; : 사용자에게 모든 권한 부여





<Resource auth="Container" driverClassName="com.mysql.cj.jdbc.Driver" maxIdle="4" maxTotal="8" name="jdbc/member" password="ais7" type="javax.sql.DataSource" url="jdbc:mysql://49.50.160.48:3306/kdt13?useSSL=false&amp;CharacterEncoding=UTF-8&amp;useUnicode=true" username="ais7"/>



# WAS 설치

1. 패키지 툴 설치 및 업그레이드

​	apt update : 패키지 툴 설치

​	apt upgrade	: 업그레이드

2. java 설치

​	apt install openjdk-8-jdk : java 8 설치(9이상은 지원안함)

​	cd /usr/lib/jvm  -> ls : 자바설치 확인

3. tomcat 설치 및 실행

​	톰캣홈페이지 -> download -> 9 ->tar.gz ->링크복사->putty에 wget 복붙(url) : tomcat 설치

​	mkdir /opt/tomcat : 폴더생성

​	mv apache.tar.gz / opt/tomcat : 폴더로 톰캣이동

​	cd /opt/tomcat : 폴더로 이동

​	chmod 777 :  모두 공유가능하게 모드 해제

​	tar xvf apache.tar.gz : 압축해제

​	cd bin -> ./startup.sh : tomcat 실행 (./shutdown.sh : tomat 끄기)

4. ACG에 추가

​	ACG에 0.0.0.0  /   8080   /   톰캣    추가 후 적용

​	웹브라우저에 공인IP : 8080 으로 접속 -> tomcat 보임







# FileZilla Client 설치

> 팀프로젝트 리모트 사이트에 업로드

1. 파일> 사이트 관리자 > new site

​	프로토콜 : SFTP / 호스트 : PUTTY에 등록한 IP  /IP  포트 : PUTTY에 등록한 port

2. 로컬사이트 -> 리모트 사이트(/opt/tomcat/apache-tomcat-9.0.56/webapps)

   리모트사이트 위치 설정후 -> 로컬사이트에서 업로드하기

   1) /opt/tomcat/apache-tomcat-9.0.56/conf  에서 context.xml(WAS->MySQL) 수정 작업이 필요(id,pwd,IP)
   2) 웹.war 파일은 /opt/tomcat/apache-tomcat-9.0.56/webapps에 올리기

3. tomcat off -> on    

   context.xml 설정을 변경했으면 tomcat을 껐다가 켜줘야됨

   ./shutdown.sh : tomat 끄기

   ./startup.sh : tomcat 실행 



# tomcat manager

1. context.xml 수정

   cd /opt/tomcat/apach~/webapps/manager/META-INF

​		vi context.xml  -> valve 부분 주석처리

2. conf 수정

​		cd /opt/tomcat/apach~/conf

​		vi tomcat-users.xml

​		role 부분 수정(manager-gui, manager-script, manager-status추가, username,password 설정)

3.  등록한 거

​		id : tomcat_admin

​		pwd : mcsn

​		manager 주소 : http://49.50.160.48:8080/manager

​		team prj 주소 : http://49.50.160.48:8080/hospital/login_form