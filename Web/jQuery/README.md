# 사용이유

1. 선택자를 사용하여 쉽게 태그 사용
2. 라이브러리 관리
3. 보통 검증 작업에 사용됨



# 문서 객체 생성과 추가

준비작업 : $(객체).ready(function(){~}) : 

```html
<script>
	$(doucment).ready(function(){~});
</script>
```



# 플러그인

라이브러리 import by  참조 or CDN(네트워크)



# 메소드

> $('객체').메소드()

* .val() : 값 가져오기, 설정하기

* .click() : 클릭하면 실행(radio,checkbox,button)

* .change() : 바뀌면 실행(select)

```js
$('#email').change(function(){~})
```

* .attr("속성",값) : 속성 값 변경

```js
$('#email').attr("disabled",true);
```

* .length 

```js
var size = $('input[class="langs"]:checked').length;
```

* .text() : value아닌 text 가져오기, 설정하기

  ex) <td id="c_name">text<td>

```js
$('#c_name').text('사용자이름')
```

* .html() : 특정 객체에 html문 작성

```js
$('#choice_box').html('<input type="checkbox" id="direct">선택');
```

* .val() : value 값 가져오기

  ex) <input type="text" value="~">

```java
$('#choice_box').val();
```

