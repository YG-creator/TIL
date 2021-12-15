# JSP

동적처리

<%%> : 자바코드 사용 / 스크립트릿

<%out.println();%> : 웹페이지에서 출력

<%=%> : 웹페이지에 변수 출력

server- client 사이 쉽게 전달함



# Request 객체

>  기능 : Client 정보 받아오기

가져오는 정보 UTF-8로 설정

```sql 
request.setCharacterEncoding("UTF-8");
```

변수 하나가져오기

```sql
request.getParameter("변수이름")
```

변수 여러개 가져오기

```sql
request.getParameterValues("변수이름")
```

