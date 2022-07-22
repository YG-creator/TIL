# 1. Git 개념

* 분산버전관리시스템



# 2. Git 특징

* 버전을 공유함

* 파일에 비해 용량이 작음(snpashot 차이점만 저장)



# 3. Git flow

Working directory->staging area->HEAD

Working directory : 로컬 저장소에서 수정한 파일

staging area :  commit할 목록

HEAD : version



# 4. 명령어

## 1. 초기 설정



### 1. git 저장소 만들기

```bash
$ git init
```

* `.git` 폴더가 생성되며, 버전이 관리되는 저장소



### 2. 파일 생성

> touch 파일이름.형식

```bash
$ touch a.txt
```



### 3. 사용자 정보 설정하기(이름,이메일)

```bash
$ git config --global user.name "YG-creator"

$ git config --global user.email "2016272046@yonsei.ac.kr"
```



## 2. 버전 만들기

### 1. `add`

> commit 할 변경사항들을 staging area에 추가

```bash
$ git add <파일/폴더/디렉토리>
$ git add . # 현재 디렉토리 변경 모두
$ git add a.txt   # 특정 파일
$ git add folder/ # 특정 폴더 
$ git add *.png   # 특정 확장자
```



### 2. `commit` 

> 변경사항들을 version에 기록

```bash
$ git commit -m 'first commit'
[master (root-commit) 16cb39b] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt

```



## 3. 상태 관련 명령어

### 1. `status` 

> add 확인

1. add 됐는지 확인

   add 안했으면 Untracked files 출력

   add 했으면 Changes to be committed 출력

2. add한 파일과 현재 파일이 같은지 확인

   같으면 초록색으로 출력

   다르면 빨간색으로 출력

### 2. `log`

> commit 확인

```bash
$ git log
```

#### log option

> -1 : 제일 최신정보 출력

```bash
$ git log -1
commit 16cb39bcf7089042fb8e25e2d2dbbc5b7324ddb9 (HEAD -> master)
Author: YG-creator <2016272046@yonsei.ac.kr>
Date:   Wed Sep 29 15:19:47 2021 +0900

    first commit
```

> -- oneline : commit 한거만 출력

```bash
$ git log --oneline
16cb39b (HEAD -> master) first commit
```

> 둘다 같이 쓸수도 있음

```bash
$ git log -1 --oneline
16cb39b (HEAD -> master) first commit
```















