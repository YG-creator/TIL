# Git

> 분산버전관리시스템
>
> 버전을 공유함
>
> 파일에 비해 용량이 작음(snpashot 차이점만 저장)

Working directory->staging area->HEAD

Working directory : 수정한 파일

staging area :  commit할 목록

HEAD : version

## git 저장소 만들기

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/test/.git/

(master) $
```

* `.git` 폴더가 생성되며, 버전이 관리되는 저장소
* git bash에서는 `(master)` 로 브랜치가 표기 된다.



## 파일 생성

> touch 파일이름.형식

```bash
$ touch a.txt
```



## 사용자 정보 설정하기(이름,이메일)

```bash
YG@YG MINGW64 ~/Desktop/test1 (master)
$ git config --global user.name "YG-creator"

YG@YG MINGW64 ~/Desktop/test1 (master)
$ git config --global user.email "2016272046@yonsei.ac.kr"
```



## 버전 만들기

### `add`

> commit 할 변경사항들을 staging area에 추가

```bash
$ git add <파일/폴더/디렉토리>
$ git add . # 현재 디렉토리 변경 모두
$ git add a.txt   # 특정 파일
$ git add folder/ # 특정 폴더 
$ git add *.png   # 특정 확장자
```

#### 예시

```bash
$ touch a.txt
$ git status
On branch master

No commits yet
# 트래킹되지 않는 파일 / Working directory
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt

nothing added to commit but untracked files present (use "git add" to track)
$ git add a.txt
$ git status
On branch master

No commits yet
# 커밋될 변경사항들!!! (Staging area)
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

```

### `commit` 

> 변경사항들을 version에 기록

```bash
$ git commit -m 'first commit'
[master (root-commit) 16cb39b] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt

```



## 상태 관련 명령어

### `status` 

> 1번째 통, 2번째 통 상태 확인

#### 예시

```bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt
```



### `log`

> 3번째 통 상태 확인

#### 예시

```bash
$ git log
commit 16cb39bcf7089042fb8e25e2d2dbbc5b7324ddb9 (HEAD -> master)
Author: YG-creator <2016272046@yonsei.ac.kr>
Date:   Wed Sep 29 15:19:47 2021 +0900

    first commit

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
YG@YG MINGW64 ~/Desktop/test1 (master)
$ git log -1 --oneline
16cb39b (HEAD -> master) first commit
```















