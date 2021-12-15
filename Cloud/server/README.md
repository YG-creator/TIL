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
공용 IP : 49.50.160.48



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