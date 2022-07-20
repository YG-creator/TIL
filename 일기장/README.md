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



4/6

1. 최소공배수 + 최대공약구 - 유클리드 호제법

2. 1차 dp - dp[i] = dp[i-3] + dp[i-2] + dp[i-2] , 

   테스트케이스 여러개인경우 dp[최댓값]까지 저장후 dp[n] 호출

3. 백트래킹 (중복ㄴ 순열) -  틀림

4. 최단거리(다익스트라) - 틀림



4/7

1. 완전탐색 - n~1까지 연산값 최댓값 구하기
2. bfs - 덩어리 요소 갯수 세기
3. 2차 dp -  못품
4. bfs + 구현 - 틀림



4/8

1. 이진수 덧셈

2. 2차 dp - 연속 불가능 + 더하기  -

   %연산자가 + 연산자보다 우선순위 높아서 () 필요

3. 누적합 + 아스키코드

4. 위상정렬 - 틀림(메모리 초과)



4/9

1. 문자열 - 값 비교 

   ​			  값이 계속 변경되면 출력은 변경 다하고 출력하기

2. 백트래킹 - 같은것이 있는 순열

3. 구현 - h+1 화살 있으면 h+1화살 갯수 1개 감소 && h화살 1증가   /  없으면 h화살 1추가

4. 위상정렬 - 간선추가할때 indegree[child]++, indegree[x] == 0 일때 q에 추가,  res.size() != n이면 사이클



4/10

1. 문자열 - substing, replace, charAt(), indexOf
2. 다익스트라 - PriorityQueue, visited
3. 구현 - 이동->합치기->나누기->무게합
4. 완전탐색 - 행>=n이면 끝,열>=이면 r+1,0



4/11

1. 문자열 - 연속된 문자열 비교
2. 구현 - 회전을 배열로 표현하기
3. 이분탐색 - 차이 최댓값 최솟값 구하기(차이 최댓값, 구간 갯수)
4. bfs - 최단거리(범위, 중복(3개변수), 조건)



4/12

1. 그리디 - h 정렬후 h[i]가 L보다 작거나 같으면 L++  /  아니면 break
2. bfs - 최단거리(큐,범위,중복)
3. 1차 dp  : dp[i] = dp[i-1] * 2   /    짝수이면 dp[i] = dp[i-4] + dp[i-5] 
4. krustal - 최단거리(pq, union, find) + 남여 edge만 추가 + 모두연결되었는지 확인(find)



4/13

1. 완전탐색 - 같은 숫자 안들어간 번호 세기
2. 완전탐색 - 첫글자 or 마지막글자 넣어서 가장 빠른 문자열 출력
3. 완전탐색 - CCTV 5종류 구현 + 사각지대 최소
4. 트리- 트리의 순회(중위+후위 -> preorder)



4/14

1. 정렬 - Arrays.sort()
2. 최단거리(플로이드 와샬) - 다수 최단거리
3. bfs - 특수한 이동(2배, 10배+1)
4. krustal - 최단거리(pq, w오름차순) + sum(w+cnt*t)



5/11

1. 구현 - 그래프
2. 다똑같은지 확인(완전탐색) + 아니면 9등분(재귀)
3. 최단거리(bfs) + 그래프 이동
4. 투포인터



5/13

1. 공간복잡도 : int 형이 1000만 이하이어야 가능
2. 그리디 : 정렬 or pq



5/16

1. [코스튬 파티 #6159](https://www.acmicpc.net/problem/6159) 

   완전탐색

   nC2 + 조건(두수의 합이 k 이하인거 세기)  -> 시간복잡도 4e8이므로 완전탐색 

2. [링크와 스타트 #15661](https://www.acmicpc.net/problem/15661)

   완전탐색

   2개로 분류하기-> 완전탐색(뽑기,안뽑기) -> 시간복잡도 2^20이므로 사용 -> 팀 분류 후 점수 각각 구하기 -> 최소 점수차만 출력

3. [작업 #2056](https://www.acmicpc.net/problem/2056)

​		DP

​		이전거 영향을 받음 -> dp[now] = Math.max(dp[prev] ) + time[now] -> dp의 최댓값 출력

4. [양팔저울 #2629](https://www.acmicpc.net/problem/2629)

   DP

   완전탐색 -> 시간복잡도 3^30 -> 시간초과 -> 중복값 처리 필요 -> 메모제이션 사용하기

   이전거 영향받음 + 메모제이션-> dp(idx, 숫자)  -> 방문처리 + dfs(idx+1, 안뽑기 or 더하기 or 빼기)




5/17

1. [로프 #2217](https://www.acmicpc.net/problem/2217)

   그리디(완탐, dp 안됨)

   완전탐색 -> 시간 복잡도 : 1e10 -> 

   dp -> 이전거 영향 안받음

   그리디 -> 정렬 -> Math.max(w[i] * (n-i)) 구하기

2. [토마토 #7569 ](https://www.acmicpc.net/problem/7569) v

   bfs(그래프 + 가중치 일정 + 최단거리)

   1인거만 q에 넣기 -> q가 빌때까지 다 한칸씩 이동 -> 0이 있으면 -1 출력  /  없으면 days 출력

   주의점 :   for문에 변수를 사용할 때 변하는 값을 넣으면 답이 틀림

3. [비밀 모임 #13424](https://www.acmicpc.net/problem/13424)

   플로이드 와샬

   a to x + b to x -> 여러개의 최단거리 필요 -> 플로이드 워셜 -> 시간복잡도 : 100 ^ 3 <1e9 사용가능

4. [마법사 상어와 토네이도 #20057](https://www.acmicpc.net/problem/20057)  v

   구현

   토네이도 이동 + 모래이동

   주의 : 소숫점 버리기



5/18

1. [카드 놓기 #18115](https://www.acmicpc.net/problem/18115) 

   덱

   맨위, 두번째, 맨아래 : 값을 넣을 때마다 달라짐

   맨위 - 맨위 다음위치에 값이 없으면 idx1++    /   있으면 idx1 = idx2 + 1

   두번째 - 맨위 다음위치에 값이 없으면 idx2 = idx1 + 1  /  있으면 idx2 = idx1 + 1

   맨아래 - 값을 넣을 때마다 idx3--

2. [주지수 #15724](https://www.acmicpc.net/problem/15724) 

   누적합

   n이 1e5이므로 완전탐색 불가 + 구간합 -> 누적합 사용 (O(n))

​		1행, 1열, 2행2열 ~ n행 n열 누적합 구하기  -> 구간합 구하기

3. [세부 #13905](https://www.acmicpc.net/problem/15724)

   다익스트라

   s(1개) to e(1개) 최댓값 -> 완전탐색은 시간초과 -> 다익스트라

   n,m 입력 -> s,e 입력 -> 간선정보 입력 -> dist[], pq, visited[] 초기화 -> pq에 (s,INF) 넣기 -> 방문안했고, dist[i] 보다 큰 값일 때만 dist 변경 및 pq에 추가

   주의점 : 다익스트라는 pq.poll()한 다음에 중복처리 해야됨

   ​				pq에 추가하는 것은 연결된 e, w

   ​				pq 정렬 기준은 w 내림차순

4. [공주님의 정원 #2457](https://www.acmicpc.net/problem/2457)

   그리디

   완전탐색은 시간초과 -> 그리디(Olog(n) + n)

   시작시간, 끝시간 입력(100 * 월 + 일) -> 정렬(시작 오름차순, 끝 오름차순) -> 범위 안에 들어오면 cnt++ -> 기준 변경



1. 구간합 -> 누적합으로 구하기
2. 다익스트라 중복처리 순서 주의 (poll 다음)
3. 그리디는 정렬



5/19

1. [정수 제곱근 #2417](https://www.acmicpc.net/problem/2417)

   이분탐색

   0~2^63 이므로 완전탐색 불가능 + 제곱근 찾기 -> 이분탐색

   s=0, e=n으로 초기화 -> while(s<=e) {m = (s+e) / 2 ,    m*m >= n이면 e = m-1   /   m*m < n이면 s=m+1 } -> s 출력

2. [잃어버린 괄호 #1541](https://www.acmicpc.net/problem/1541)

   완전탐색

   시간복잡도 O(n) 이므로 완전탐색 가능

   문자열(숫자, 기호 파싱) -> 순열(연산 순서 정하기) -> 완전탐색(연산 순서대로 연산하기) -> 최솟값 저장 -> 최솟값 출력

3. [연속합 2 #13398](https://www.acmicpc.net/problem/13398)

   2차 DP + 누적합

   완전탐색 O(n^2) 시간초과 + 이전거 영향받음 -> DP  -> 인수 : 번째 , 제거여부 -> 2차 DP

   연속 구간합 -> 누적합

   ```java
   sum[i][0] = Math.max(sum[i-1][0]+nums[i], nums[i]);
   sum[i][1] = Math.max(sum[i-1][0],sum[i-1][1]+nums[i]);
   ```

4. [색종이 3 #2571](https://www.acmicpc.net/problem/2571)

   누적합

   연속구간 최대넓이 -> 누적합

   x축 기준으로 누적합 구하기 -> (h1~h2 에서 최솟값) * 길이 의 최댓값 구하기



5/20

1. [할아버지는 유명해! #5766](https://www.acmicpc.net/problem/5766) 

   구현(map)

   매주 랭킹에 선수의 이름이 오를 때마다 선수의 포인트가 1포인트씩 오름 -> 2등 출력

2. [안녕 #1535](https://www.acmicpc.net/problem/1535) 

   완전탐색 or DP

   1. 완전탐색(2^32) 가능 -> 인사하기(체력0 보다 클때만) or 인사안하기 -> 최솟값 출력

   2. DP(21 * 100) 가능

      ```java
      if(j>=L[i]) dp[i][j] = Math.max(dp[i-1][j],dp[i-1][j-L[i]]+J[i]);
      else dp[i][j] = dp[i-1][j];
      ```

3. [나무 탈출 #15900](https://www.acmicpc.net/problem/15900)

   DFS

   루트노드 ~ 리프노드 거리 다 더하기

   1부터 시작해서 연결된게 1개가 나오기 전까지 dfs -> 연결된게 1개가 나오면 ans += cnt

4. [안정적인 네트워크 #2406](https://www.acmicpc.net/problem/2406)

   최소스패닝 트리(pq, parent[], union, find)

   1제외하고 다 연결하기 + 최소 비용 -> 최소스패닝 트리

   parent 초기화 -> 이미 연결된거 union 처리 -> Edge 중 1과연결 된거 제외하고 pq에 넣기 -> 연결안된거만 연결하기 -> 최소비용 출력



5/23

1. [숫자 야구 #2503](https://www.acmicpc.net/problem/2503) 

   완전탐색

   9개중에 3개 뽑기 -> 게임마다 strike, ball 구하기 -> 모든 게임의 strike와 ball 일치하는지 확인 -> 모두 일치하면 cnt++

2. [숨바꼭질 4 #13913](https://www.acmicpc.net/problem/13913) 

   bfs

   s to e 최단시간 -> 완전탐색 -> 시간초과(O(V^2))

   s to e 최단시간 /  +1,-1,x2 이동  && cost는 1로 동일 -> bfs  

   경로추적 - 전 값을 저장(parent[]) + Stack(LIFO)

3. [사다리 조작 #15684](https://www.acmicpc.net/problem/15684) v

   백트래킹

   n개중 i개 뽑기 + 사다리타기 결과 확인(dfs)

4. [순회강연 #2109](https://www.acmicpc.net/problem/2109)

   그리디

   완전탐색 -> 시간초과(O(V^2))

   DP -> 이전거 영향 안받음

   bfs-> cost가 일정하지 않음

   그리디 -> 정렬(내림차순) -> O(V) -> 가능



5/24

1. [게임을 만든 동준이 #2847](https://www.acmicpc.net/problem/2847)

   그리디

   뒤에서 부터 최솟값보다 작게 만들기

2. [1, 2, 3 더하기 7 #15992](https://www.acmicpc.net/problem/15992)

   2차 DP(숫자, 갯수)

   ```java
   dp[n+1][cnt+1] += dp[n][cnt];
   dp[n+2][cnt+1] += dp[n][cnt];
   dp[n+3][cnt+1] += dp[n][cnt];
   ```

   

3. [목장 건설하기 #14925](https://www.acmicpc.net/problem/14925)

   DP

   해당 영역이 들판일 때만 Math.min(좌,위,왼쪽위 대각선) 저장

   

5/25

1. [암기왕 #2776](https://www.acmicpc.net/problem/2776) 

   이분탐색 - nums[] 안에 num 있는지 여부 확인

   완전탐색 -> O(MN) -> 시간초과

   이분탐색 -> O(logN) -> 가능 -> 정렬 후 -> 이분탐색

2. [단축키 지정 #1283](https://www.acmicpc.net/problem/1283) 

   set(중복) + 문자열 파싱(처음, 왼->오)

3. [1,2,3 더하기 6 #15991](https://www.acmicpc.net/problem/15991)

   2차 dp

   완전탐색 -> O(3^n*n) -> 시간초과

   양쪽에 같은 수 더하기 -> dp -> dp[i] = dp[i-2] + dp[i-4] + dp[i-6]  -> 초기값 6까지 해줘야됨(예외)

4. [크게 만들기](https://www.acmicpc.net/problem/2812)

   Stack

   왼쪽거 보다 크면 왼쪽거 k개 까지 삭제 -> 아니면 추가 -> 모두 숫자가 같은경우 주의



5/26

1. [NBA 농구 #2852](https://www.acmicpc.net/problem/2852)

   Stack(LIFO) + 문자열(파싱)

   승리 -> 무승부  /   승리~마지막

2. [여러분의 다리가 되어 드리겠습니다! #17352](https://www.acmicpc.net/problem/17352)

   분리집합

   다 연결하기 -> union-find

3. [서강그라운드 #14938](https://www.acmicpc.net/problem/14938)

   플로이드 워셜

   i to j 거리 구하기 + 조건(m보다 작아야됨) -> sum(item[j])

4. [LCS 3 #1958](https://www.acmicpc.net/problem/1958)

   3차 dp

   ```java
   // 같은 경우
   dp[i][j][k] = dp[i-1][j-1][k-1] + 1;
   // 다른 경우
   dp[i][j][k] = Math.max(dp[i-1][j][k],dp[i][j-1][k],dp[i][j][k-1])
   ```

   

   

5/27

1. [에라토스테네스의 체 #2960](https://www.acmicpc.net/problem/2960)

   다수 소수 판별

2. [1, 2, 3 더하기 8 #15993](https://www.acmicpc.net/problem/15993)

   2차 dp(합,홀짝)

3. [점프왕 쩰리 (Large) #16174](https://www.acmicpc.net/problem/16174)

   bfs(특정 숫자만큼 직진 이동) - 범위, 중복처리

4. [동전 분배](https://www.acmicpc.net/problem/1943) v

   dp(냅색)

   dp[j-v] == true -> dp[j-v+v*k] = true



5/30

1. [균형잡힌 세상 #4949](https://www.acmicpc.net/problem/4949)

   Stack(LIFO)

   균형잡힌 괄호 여부 확인

2. [유기농 배추 #1012](https://www.acmicpc.net/problem/1012)

   BFS

   덩어리 갯수 세기

3. [불장난 #14945](https://www.acmicpc.net/problem/14945) v

   DP

   완전탐색 -> 2^100 -> 시간초과

   이전거 영향(아래, 오른쪽 대각선 이동) + O(n^2) -> dp

4. [후위 표기식 #1918](https://www.acmicpc.net/problem/1918) v

   Stack

   Last가 우선순위가 높으면 pop + 괄호 연산은 우선순위가 가장 낮음 



5/31

1. [Four Squares #17626](https://www.acmicpc.net/problem/17626) v

   dp

   그리디 - 높은값부터 더함 -> 틀림

   완전탐색 - > 시간초과

   이전거 영향 + 완전탐색 -> dp - > dp[i] = Math.max(dp[i-j*j]) + 1

2. [친구 #1058](https://www.acmicpc.net/problem/1058)

   완전탐색 - O(50^2) - 친구 or 친구의 친구 세기

3. [나의 인생에는 수학과 함께 #17625](https://www.acmicpc.net/problem/17265) 

   dfs

   그래프이동 + 최댓값 + 최솟값 -> dfs

4. [욕심쟁이 판다 #1937](https://www.acmicpc.net/problem/1937) v

   dfs + dp

   완전탐색 + dfs(그래프 이동) -> 시간초과 

   완전탐색 + dfs(그래프 이동) + dp(4방향, 현재 값중 최댓값 고르기) -> 해결

   

   6/1
   
   1. [LCM #5347](https://www.acmicpc.net/problem/5347) v
   
      최소공배수 - 유클리드 호제법
   
   2. [원상 복구 (small) #22848](https://www.acmicpc.net/problem/22858) 
   
      구현
   
      order[d[j] - 1] = s[j] 반복
   
   3. [단절점과 단절선 #14675](https://www.acmicpc.net/problem/14675) v
   
      트리 (단절점, 단절선) -> 리프 or 루트노드 찾기 -> 간선이 1개인거 찾기
   
      아무선 하나만 잘라도 2개로 나눠짐
   
      내부노드를 제거하면 2개로 나눠짐
   
   4. [웜홀 #1865](https://www.acmicpc.net/problem/1865) v
   
      벨만포드
   
      음의 가중치 -> 벨만포드 -> 음의 순환여부 확인 -> n-1 upadte 이후 update되면 음의 순환 있는거
   
   

최소공배수, 리프or루트노드 찾기, 벨만포드



6/2

1. [아이폰 9S #5883](https://www.acmicpc.net/problem/5883)

   완전탐색

   완전탐색 -> O(1000^2) -> 가능

   1. 모든 숫자 종류 구하기 -> set

   2. 숫자 한종류만 빼서 최대연속 구간구하기 -> 완전탐색

2. [관악산 등산 #14699](https://www.acmicpc.net/problem/14699) v

   완전탐색 + dfs + dp

   완전탐색 or dfs -> 시간초과 -> 완전탐색 + dfs + dp

   1. 시작점 -> 완전탐색
   2. 연결된거 && 높은거만 이동 -> dfs
   3. dp 값이 있으면 그값 return -> dp   /   dp[now] = Math.max(dp[now], dp[next] + 1)

3. [드래곤 커브 #15685](https://www.acmicpc.net/problem/15685) v

   구현(회전)

4. [우주신과의 교감 #1774](https://www.acmicpc.net/problem/1774) v

   최소 스패닝 트리

   최단거리 + 다연결하기 -> 최소스패닝 트리

   1. 이미 연결된거 입력 -> 분리 - 집합
   2. pq에 시작점, 끝점, 거리(위치로 구하기)
   3. 연결안된거만 연결하기  -> 분리 - 집합

​			주의 : 거리 자료형 double로 하기 ++ 

​					 소숫점 표현식 = String.format(".nf",ans)

6/3

1. [카드 놓기 #5568](https://www.acmicpc.net/problem/5568)

   백트래킹(중복ㄴ순열) + set(중복제거)

2. [블로그 #21921](https://www.acmicpc.net/problem/21921)

   누적합

3. [숫자 재배치 #16943](https://www.acmicpc.net/problem/16943)

   백트래킹(중복ㄴ순열) + 크기비교

4. [수확 #1823](https://www.acmicpc.net/problem/1823)

   dfs + dp



6/4

1. [수리공 항승 #1449](https://www.acmicpc.net/problem/1449)

   그리디(정렬) 

   정렬 -> 기준치보다 크거나 같으면 cnt++

2. [준표의 조약돌 #15831](https://www.acmicpc.net/problem/15831)

   누적합

   연속구간 갯수 세기 -> 최소, 최대 조건 따지기

3. [랭퍼든 수열쟁이야!! #15918](https://www.acmicpc.net/problem/15918) v

   백트래킹

   중복 2개 순열 + n과 n사이에는 n개의 숫자 + 1개는 고정

4. [커플 만들기 #1727](https://www.acmicpc.net/problem/1727) v

   그리디 + dp

   그리디 + 완전탐색 -> 시간초과(O(100^1000))

   그리디 + dp -> 가능

   ```java
   1. 남자 여자 정렬
   2. dp[i][j] = dp[i-1][j-1] + Math.abs(men[i]-women[j])
   3. 남자가 안만나는 경우 + 여자가 안만나는 경우
   if(i > j) dp[i][j] = Math.min(dp[i][j],dp[i-1][j])
   else if(i < j) dp[i][j] = Math.min(dp[i][j],dp[i][j-1])
   ```




6/6

1. [스택 #10828](https://www.acmicpc.net/problem/10828)

   스택

   push, pop, isEmpty(), size()

2. [휴게소 세우기 #1477](https://www.acmicpc.net/problem/1477)

   이분탐색

   1. 최대거리의 최솟값 구하기 
   2. cnt += 거리 / mid 
   3. cnt < m 이면 e = m-1   /  cnt > =m 이면 s = m+1

3. [회전 초밥 #15961](https://www.acmicpc.net/problem/15961)

   슬라이딩 윈도우

   1. 초기값(연속 k개)
   2. 처음거 빼고 다음거 더하기 반복

4. [역사 #1613](https://www.acmicpc.net/problem/1613)

   플로이드 와샬

   여러개 전후관계 따지기 -> 단방향 그래프 



6/7

1. [별 찍기 - 19 #10994 ](https://www.acmicpc.net/problem/10994)

   재귀

   한변의 길이가 4n-3 인 정사각형 그리기 반복(위,아래,왼,오)

2. [배열 돌리기 3 #16935](https://www.acmicpc.net/problem/16935) 

   구현(회전(90,-90), 대칭(상하,좌우), 덩어리 회전)

3. [퍼레이드 #16168](https://www.acmicpc.net/problem/16168) vv

   오일러 경로

   한붓그리기

4. [궁금한 민호 #1507](https://www.acmicpc.net/problem/1507) vv

   역 플로이드 와샬

​		플로이드 와샬 -> 같은지점으로 이동 continue  /  거리가 짧아지면 -1 return  / 같은거리가 있을 경우 제거(INF) -> INF 아니고, 방문안한거 다더하기



6/8

1. [수들의 합 2 #2003](https://www.acmicpc.net/problem/2003)

   누적합

   누적합이 m이면 cnt++, 작으면 e++, 크면 s++

2. [파닭파닭 #14627 ](https://www.acmicpc.net/problem/14627) vv

   이분탐색

   1. s = 1, e=1e9
   2. 이분탐색
   3. sum - c * e

   주의 :  자료형

3. [토마토 #7576](https://www.acmicpc.net/problem/7576)

   bfs

   퍼지기 -> bfs -> 1칸씩 이동 -> 다 이동하면 0있는지 확인

4. [나무 재테크 #16235 ](https://www.acmicpc.net/problem/16235) v

   구현 + bfs + Queue + 완전탐색

   1. 봄 : 나이만큼 양분을 먹고, 나이가 1 증가, 양분을 먹지 못하고 즉시 죽는다 - q.poll(),q.add()
   2. 여름 : 죽은 나무마다 나이를 2로 나눈 값이 나무가 있던 칸에 양분으로 추가, 소숫점 버림 - q.poll()
   3. 가을 : 나무는 나이가 5의 배수이어야 하며, 인접한 8개의 칸에 나이가 1인 나무가 생긴다, 범위안이어야 됨 - bfs
   4. 겨울 : 영양분 추가 - 완전탐색



6/10

1. [GCD 합 #9613](https://www.acmicpc.net/problem/9613) v

   최대 공약수

   x의 공약수 구하기(1~루트x) -> 약수 내림차순 정렬 -> y % 약수 == 0 인거 찾기

2. [나무 자르기 #14247](https://www.acmicpc.net/problem/14247) v

   그리디

   Ai를 기준으로 오름차순 정렬 -> ans += Hi + Ai * i

   자료형 주의

3. [1,2,3 더하기 9 #16195](https://www.acmicpc.net/problem/16195) v

   2차 dp - 합, 더한 숫자 갯수

   ```java
   dp[i][j] += dp[i-k][j-1]
   ```

4. [택배 #1719 ](https://www.acmicpc.net/problem/1719) v

   플로이드 와샬

   거리가 짧아질때 갱신




6/12

1. [적록색약 #10026](https://www.acmicpc.net/problem/10026)

   bfs

   조건만 변경(적색, 녹색)

2. [빗물 #14719](https://www.acmicpc.net/problem/14719) v

   구현

   왼쪽 최댓값, 오른쪽 최댓값 구하기 -> ans += (왼쪽, 오른쪽 최솟값 - 높이)

3. [게임 개발 #1516](https://www.acmicpc.net/problem/1516) vv

   위상정렬

   순서 정하기



6/13

1. [Maximum Subarray #10211](https://www.acmicpc.net/problem/10211)

   누적합

   연속구간합 최댓값 구하기 -> 누적합 -> 완전탐색 sum[i] - sum[j] (j<i) 최댓값 구하기

2. [쉬운 최단거리 #14940](https://www.acmicpc.net/problem/14940)

   bfs

   그래프 최단거리 -> bfs(Queue)

   1. 출발점 0으로 출발
   2. 상하좌우 이동
   3. 범위, 중복, 조건 처리
   4. 출력(바위가 아닌데 거리가 0이면 -1 출력)

3. [최소비용 구하기 #1916](https://www.acmicpc.net/problem/1916) v

   s to e 최소비용 1개 -> 다익스트라

   1. dist, edges, visited, pq 초기과 및 입력
   2. pq에 (s,0) 넣기
   3. 거리가 최소이고, 방문 안한거면 dist 값 입력
   4. dist[e] 출력

   주의 : 중복처리할 때 poll() 하고 바로 다음에 해야 됨

4. [북쪽나라의 도로 #1595](https://www.acmicpc.net/problem/1595) v

   트리의 지름 최댓값 구하기

   1. 간선 입력
   2. dfs(1,0) -> 트리의 지름이 최대인 지점 구하기
   3. dfs(start,0) -> 트리의 지름 최댓값 구하기
   4. 출력



6/14

1. [진우의 달 여행 (Small) #17484](https://www.acmicpc.net/problem/17484) v

   3차 dp (x,y,방향) + 연속 같은 방향 ㄴ

2. [색종이 만들기 #2630](https://www.acmicpc.net/problem/2630) v

   재귀(분할정복)

3. [MST 게임 #16202](https://www.acmicpc.net/problem/16202) v

   최소스패닝 트리 반복(1개씩 제거) + 다 연결됐는지 확인 

4. [박스 채우기 #1493](https://www.acmicpc.net/problem/1493) v

   분할정복 + 그리디

   1. 큰거부터 반복 
      1. before *= 8
      2. 전체 갯수 = 전체부피 / 큐브 부피 - before
      3. before, ans += Math.min(큐브갯수, 전체갯수)    
   2. before == lwh 이면 ans 출력  /  아니면 -1 출력

   자료형 주의, 비트연산 (a<<=n 은 a = a*2^n      ,    a >> i 는 a / 2^i) 

   

6/16

1. [2+1 세일 #11508](https://www.acmicpc.net/problem/11508)

   그리디

   내림차순 정렬 -> 3번 째마다 빼고 더하기

2. [타일 채우기 3 #14852](https://www.acmicpc.net/problem/14852) v

   2차 dp

   ```java
   dp[i] = dp[i-1]*2 + dp[i-2]*3 + 2*(dp[i-3] + ... dp[i-n])
   
   // 시관초과 -> 2*(dp[i-3] + ... dp[i-n]) -> 2차 dp로 해결
   dp[i][1] = dp[i-1][1] + dp[i-3][0]
   dp[i][0] = dp[i-1][0]*2 + dp[i-2][0]*3 + 2*dp[i][1]
   ```

3. [행성 연결 #16398](https://www.acmicpc.net/problem/16398) 

   MST

   최단거리 + 다연결 -> MST

   자료형 주의

4. [파티 #1238](https://www.acmicpc.net/problem/1238)

   플로이드 와샬

   i -> x -> i 최단거리 + 단방향 그래프



7/19

1. 완전탐색 + bfs
2. 완전탐색 + 문자열 + 이진법
   1. s = s.replace()
   2. s = Integer.toBinaryString(num)
3. arr idx + 나머지, 몫
4. 분할정복(dfs)



7/20

1. 2차 dp
2. Stack(LIFO)
3. 완전탐색 + 이진수 변환 + 문자갯수 세기
4. 2차 dp

주의할점

1. 완전탐색부터 생각해라
2. dp 초기값 주의
