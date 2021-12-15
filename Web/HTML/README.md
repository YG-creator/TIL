# HTML

## 	개념 

​		Hyper-Text Markup Language 

​		HT = 문서와 문서가 링크로 연결됨

​		M = 태그로 이루어짐

​		L = 언어

​		

## 	구성

​		HTML = tag + attribute

​		semantic(의미론적) 구성 : head(제목) / body(내용)



## 기능

정적처리



# tag & attribute

1. h1 : 제목글자

2. p(문단),br(띄어쓰기),hr(아래밑줄)

3. 링크(a)

   href ="경로"

4. ul(순서ㄴ),ol(순서0),li(목록)

5. table, tr(행),th(속성),td(열)

   border-table

   rowspan, colspan-tr,th,td

6. img

   src="경로", alt(이미지x글자), width, height

7. form : 데이터를 서버에 전달하는 방법

   GET , POST

   text, radiobox,checkbox,select

8. 주석 : <!-- -->

9. style

10. 자바스크립트 내부 vs 외부

11. 경로

    현제 디렉토리 = "."

    상위 디렉토리 = ".."



# Input tag

1. form attribute

   action="URL"

   method = "GET(url)" or "POST"

   

2. input 

   (1) attribute

   ​	type

   ​	name

   ​	value

   (2) type

   ​	text 

   ​	password

   ​	checkbox	: 다중 선택

   ​	radio	: 단일 선택

   ​	reset

   ​	submit

   ​	button

   

3. select

   (1) attribute

   ​	name

   (2) 하위태그

   ​	option

   

4. textarea attribute

   rows

   cols

   name

   value 없음



# 문서 구조화

1. 공간 분할

   div : 블록 형식으로 공간 분할

   span : 한줄 형식으로 공간 분할

2. 시맨틱 태그 

   header : 머리말

   nav : 메뉴

   aside : 광고

   section : 그룹

   article : 본문

   footer : 꼬리말
