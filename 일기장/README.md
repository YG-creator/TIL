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



3/ 11

1. 그리디
2. bfs(최단 시간 - 중복 ㄴ, 짧은거부터) - que
3. 벨만포드(음의 순환 확인) - n-1번 이후 초기화때도 변하면 음의순환
4. dfs - 순환 명수 찾기 - visited[], finisihed[] 사용



3/ 15

1. 그리디 - 처음으로 1~n 까지 합 > sum  -> n-1 출력

2. union-find : 집합의 갯수
3. 2차 dp - 최소가격 (날짜, 쿠폰)
4. 다익스트라 - 최단거리 + 경로



3/16

1. 그리디 - 최대수용량 넘어가면 cnt++
2. dp[i] = dp[j] + (i-j)^2 의 최솟값 
3. 누적 합
4. 분리 집합 갯수 세기



3/17

1. 최소공배수 - 유클리드 호제법
2. 소수 판별 에라토스 테네스 - 다수(NloglogN), 단일(2~Math.sqrt)
3. 그래프(오른쪽, 아래쪽 이동) + dp(최솟값) + if문
4. 트리(루트노드 모름) + dfs 



3/18

1. DNA 공통글자 갯수 세기
2. 2진수
3. 3차 dp- 방향, x좌표, y좌표
4. 누적합
누적합 % m 갯수 같은거 2개 뽑기  -> (sum[i] - sum[j]) % m => sum[i] % m = sum[j] % m 을 이용
누적합 % m == 0 인경우는 혼자만 있어도 가능



3/20

1. 스택(이동 구현)
2. dfs - 부모노드 찾기(루트노드 주어짐)

3. 그리디 - 연속적이지 않은곳 세기
4. 누적합 - 반복연산 하나로 합치기 + 누적합



3/21

1. 단일 소수 판별 - 에라토스테네스
2. 백트래킹(nCr) - 취약 - idx, depth
3. LCS 공통 연속 부분수열 
4. 누적합 + 2차 dp  



3/22 

1. 투포인터 - 연속된 수들의 합
2. 브루트포스 - map으로 글자중복, index 해결
3. BFS - 최단거리(중복확인 해야 시간초과 안함)
4. bfs + 크루스칼 - pq 정렬 
return o.v >= this.v ? -1 : 1 // 오름차순



3/23

1. 문자열 정렬,대소문자 변환
2. 이분 탐색
3. 스택 - LIFO



3/24

1. 브루트포스
2. 완전탐색 재귀 - +,-,가만히    연산으로 못만드는 수 찾기
3. bfs 2개 동시 - q사이즈 만큼 q.poll 하기 	
4. krustal - 최대거리 + c와 v 연결 + 순환 ㄴ



3/27

1. 완전탐색 - 중복 없는 조합 + 특정 조합 없애기
2. bfs - 특정 이동 (텔레포트, -1,1 이동)
3. dfs - 트리의 지름 + 루트노드 구하기



3/28

1. 구간합 - 초기값 주의
2. bfs - 덩어리 갯수 세기
3. 그리디 - 2진수 1의 갯수 = 더하기 횟수 / 2진수 자릿수 -1 = 곱하기 횟수
4. 문자열 - 파싱 + 연산(월+일+시간+분 -> 분) + map(key,value)



3/31

1. 구현 - map(key-value)로 좌표 구현 + 절댓값 계산
2. bfs - 덩어리 갯수 
3. 백트래킹 - 중복없는 조합(한번에 이웃한 3개 선택 or 선택안하기)
4. 트리 - 간선 갯수 + 조합 갯수(수학,중복)



4/2

1. 스택 - LIFO
2. 문자열 - EW 찾기
3. 구현 - 도미노(높이가 높은걸로 초기화 + 서있으면 넘어뜨리기 + 과정지나면 높이--)
4. 트리(연결만 앎) + 2차 dp - 00만 불가능 



4/3

1. 다수 소수 판별 - 에라토스 테네스 ( i는 2~루트n  /   j는 i ~ n/i)
2. bfs - 덩어리 갯수
3. 다익스트라 - 최단거리(우선순위 큐 - 방문처리 미약했음)
4. 구현 - 약함



4/4

1. 1차 dp - 초기값 설정 주의
2. 2차 dp + 누적합
3. krustal(순환ㄴ+최단거리)
4. 구현 - 주사위 90도 회전 6방향



4/5

1. 투포인터	- 못풀음
2. 1차 dp - 음수 , 양수 연속구간 합(모두 음수인 경우 / 전합 + 해당 숫자 >0 인경우)
3. bfs- 한칸씩 이동(while문 안에 q.size만 큼 poll)
4. 구현 - bfs - 못풀음
