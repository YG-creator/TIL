# CSS

html 디자인



# html과 css연동

```html
<link rel="stylesheet" href="경로">
```



# 선택자

* 전체 : *
* 태그 : 그대로

* id : #

* class : .
* 후손 : 밑에있는거  -> A B
* 자손 : 바로 밑에 있는거 ->  A>B



# 단위

* % : 백분율 

* em : 배수

* px : 픽셀
* url()



# 색상

* RGB

* RGBA(투명도 포함)

* HEX : #16진수 - 선호



# 속성

1. 박스

   margin : 테두리 바깥쪽 여백

   ​				값 설정 : 위,오,아.왼 순서

   border : 테두리

   ​				종류 : -width,-style,-color,-radius(위,오,아,왼)

   padding : 테두리와 글자사이 여백

   width : 글자 가로

   height : 글자 세로

2. 가시

   none 

   block : 박스

   inline : 한줄

   inline-block : 한줄 가운데 박스

3. 위치

   position : absolute(한곳에 집중), relative(한곳 ㄴㄴ)

   left : x축 거리

   top : y축 거리

   z-index : 클수록 앞으로

   overflow : 내용이 위치를 넘으면 hiiden(숨김), scroll

4. 유동

   float : 수평정렬  /  left,right

