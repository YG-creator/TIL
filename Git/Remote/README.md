# 원격저장소 활용

원격저장소 활용을 하기 위해서는 GitHum 사이트에서 직접 만들어야한다.

## 원격저장소 등록 및 추가

```bash
$ git remote add origin https://github.com/YG-creator/TIL.git
$ git push -u origin master
```

> 이름origin으로 원격 저장소 추가(add) 
>
> 기본 원격저장소를 origin master로 설정하고 보내기, 이후에는 push만 해도 됨



## 원격저장소 확인

```bash
$ git remote -v
```



## 원격저장소 삭제

```bash
$ git remote rmv origin
```



#  원격저장소 -> 로컬저장소

`pull` 커밋들만 가지고온다.

`colon `원격저장소 자체를 가져온다.

`압축파일` .git 파일 X -> 새롭게 `init`하면 새로운 로컬저장소가 됨.



같은 파일 작업 할 때

pull -> Merge commit -> 해결

여러명이 같은 파일 작업할때 pull, push가 힘듦 -> branch 사용



GitHub Pages

로컬저장소->원격저장소(username.github.io)->push
