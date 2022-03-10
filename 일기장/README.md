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



12/16

병원정보에 거리 추가
상세정보 링크 누르면 - 병원정보 출력
병원 맵에 마커
약국 리스트 출력
약국 상세정보 출력

포도농장 관리 - GP 수정 (해당 행만 수정) 해야됨

입력 하나로 묶어야됨



12/17

병원상세 정보> 리뷰게시판에 평가게시판 구현

평가등록 구현

현재위치 마커 이미지 변경

cloud server WAS 설치 -> 업로드



12/ 18

멘토링 받음

휴원게시판(리스트 없애고, 내글만 수정, 등록기능만 구현)

데이터셋 준비 필요

모든페이지에 메인페이지 링크

메인페이지 default 처리 해야됨

휴원 반영(날짜 시간) 필요



12/19 

DB프로젝트 - 요약 출력하기만 남음

챗봇 프로젝트 - 정보 위치 입력 해야됨 + 지도출력했으면 함

병원 프로젝트 - cloud server에서 tts 안됨



1/20

list 복사하기(list를 변경하지 않고 일시적으로 변경하고 싶을 때 사용)  -  ref) 코딩테스트>java>List

String 영문자 여부 확인 - ref) 코딩테스트>java>문자열

숫자 자료형(double에서 정수만 출력) - ref) 코딩테스트>java>자료형

ArrayList 에서 포함 여부 - list.contains(x);



2/4

이분탐색(특정값 찾기, 조건 만족하는 최소, 최댓값 찾기)

StringBuilder 다시 봄
문자열도 정렬 가능(Arrays.sort())
문자열 비교 : 문자열.compareTo(문자열)
array 정렬 : Arrays.sort(arr)
List 정렬 : Collections.sort(list)



2/22

트리 - 순회(전위,중위,후위), 트리+dp, 트리+dfs



2/24

BruteForce - 4차배열 사용

백트래킹-중복ㄴㄴ(visited), 오름차순 조합(start)

2차 dp 

bfs - q



2/27

문자열 비교 : str.equals()   /   == 아니다

dp 



3/2

1. 문자열 - split, substring
bw.write("str\n") or bw.newLine() 안해줘서 계속 틀렸었음
2. dp 
오른쪽 아래쪽 이동만 가능 - 최댓값 구하기
3. 구간 합
4. 트리+dp



3/ 3

1. 문자열
2. dp + 다익스트라



3/4

1. 구현
자료형 조심(NumberFormat error) - 10억 넘어가는 자연수는 long형
2. 조합 -> 백트래킹
덩어리 만들기-> bfs
3. 플로이드 와샬 - 모든지점의 최단거리
4. DFS 같아 보이지만 union-find(2차행렬->1차행렬)  해서 부모노드 찾기



3/5

1. split

   1) string을 여러 특정문자로 분리 - str.split("특정문자|특정문자"); -> | 사용

   2) `는 \\ 없이 분리 가능

   3) 문자열 배열에 특정 문자가 있는지 확인 - Arrays.asList(arr).contains(str)


2. 4차 dp

3. 두수의 합(투 포인터) 

4. union-find+ pq를 통한 quick sort



3/7

1. 자료형
double - 소숫점
2. LIS-dp
3. dp
int[] temp = dp  -> temp 변경하면 dp도 바뀜
int[] temp = dp.clone();	> temp 변경하면 dp는 안바뀜
loop:   for   break loop;
4.벨만포드



3/ 10

1. 다수 소인수 판별 - 에라토스테네스
2. dp 
3. 2차 dp
4. 그리디(누적 합)
