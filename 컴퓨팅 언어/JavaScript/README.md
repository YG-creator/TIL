# 사용법

1. html에 선언 후 사용

<script type="text/javascript">
	//코드~
</script>

2. html에 링크 후 Javascript 파일에 작성

```sql
<script type="text/javascript" src="경로"></script>
```



# 문법

자료형 ㄴㄴ

연산

주석처리 : 자바와 동일

출력 : alert("메시지") -> 경고메시지

변수 선언 : var 변수이름

조건문 : 자바와 동일

반복문 : 자바와 동일

배열 : [값] 

함수 선언 : function 함수이름(변수이름만){} - return type 선언 ㄴㄴ

함수이름 없이 사용가능 ex)

```jsp
var callback = function () {~}
```

객체(속성,메서드)



# Event

html의 태그 안에  on~("함수") : Event 수행하면 함수 호출됨

ex1)

```html
<!--JavaScript에서 함수 선언-->
<script type="text/javascript">
	function hi(){
		alert("Welcome~");
	}
</script>

<!--Event 수행시 함수실행-->
<button onclick="hi()">함수실행</button>
```

ex2)

```html
<!--JavaScript에서 함수 선언-->
<script type="text/javascript">
window.onload = function(){
	var button = document.getElementById('button');
	button.onclick = function(){
		alert('click');
	};
};
</script>

<!--Event 수행시 함수실행-->
<button id="button">버튼</button>
```

기본 이벤트 제거 - return false;



# DOM

Document Object Model 

> 웹브라우저가 html을 분석하여 출력

정적생성 - HTML 태그로 객체 생성

동적 생성 - JavaScript로 객체 생성



## 문서객체 선택(html)

1. 한개 : document.getElementById("id이름")

```sql
<!--JavaScript에서 함수선언-->
<script type="text/javascript">
function getId(){
		var ele = document.getElementById("user_id");
		if (ele.value==""){
			alert("갑을 입력하세요");
		} else{
			alert(ele.value);
		}
	}
</script>

<!--Event 발생 시 함수 호출-->
<td class="data"><input type="text" name="user_id" value="admin" id="user_id"></td>
<td><input type="button" value="id검사" onclick="getId()"></td>
```



2.  여러개 : docutment.getElementsByClassName("class이름")

```sql
<!--JavaScript에서 함수 선언-->
<script type="text/javascript">
function check_radio(){
		var eles = document.getElementsByClassName("tools");
		for(var i=0;i<eles.length;i++){
			if(eles[i].checked){
				alert(eles[i].value);
			}
		}
	}
</script>

<!--Event 발생 시 함수 호출-->
<td class="data">
				<input type="radio" name="tools" value="이클립스" class="tools">이클립스
				<input type="radio" name="tools" checked="checked" value="메모장" class="tools">메모장
				<input type="radio" name="tools" value="VSC" class="tools">VSC
			</td>
			<td><button type="button" onclick="check_radio()">단일선택확인</button></td>
```



3. document.query.Selector(선택자)   



## 속성 조작

setAttribute

getAttribute



# 함수 반복(주기)

setInterval(함수,1000);   -> 1초마다 함수 반복

clearInterval(함수); -> 반복 종료
