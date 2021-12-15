# 서버가 이미 사용 중

```java
netstat -ano | findstr 9090
taskkill /F /pid 1088
```

![img](https://i.stack.imgur.com/XiEWI.png)



# 버전 불일치 

```
message : org.springframework.dao.TransientDataAccessResourceException

Cause : Could not retrieve transation read-only status server
```

![workspace - Web Browser - Eclipse IDE 2021-11-05 오후 3_58_57](md-images/workspace%20-%20Web%20Browser%20-%20Eclipse%20IDE%202021-11-05%20%EC%98%A4%ED%9B%84%203_58_57.png)



해결

mysql5.1.29 -> mysql8.0.21로 변경  by pom.xml  

driver 변경 by jdbc.properties com.mysql.cj.jdbc.Driver로 변경



배운점

mysql에 맞게 connector 사용

mysql5.1 -> com.mysql.jdbc.Driver     /    mysql8.0 -> com.mysql.cj.jdbc.Driver



# JSON

1. list -> JSON

pom.xml에 추가

		<!-- JSON  --> 
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
			<version>2.5.4</version>
		</dependency>



2. service

```java
JSONParser parser = new JSONParser();
                JSONObject obj = (JSONObject)parser.parse(result);
                String content = (String)obj.get("text");
```



# 생성자 error

**java.lang.NoSuchMethodException soo.bin.com.<init>()**

기본생성자 생성하면 해결됨



# appservlet

pom.xml

servlet-context.xml

action-mybatis.xml

mybatis / model/ modelConfig.xml



# a 태그

> WEB-INF는 외부에서 접근 못하므로

controller로 매핑후 -> 경로를 해당 URL로 함



# Ajax 페이지 이동

1. flag = true 인지 확인
2. window.location.href('~') 확인

3. jsp에 form 태그 확인하기

4. 크롬 사용할 경우 : window.location.assign() 사용
5.  크롬 사용시, 쿠키데이터 삭제



# js error

uncaught referenceerror $ is not defined

js 보다 앞에 jquery 선언해줘야됨



# git 용량 초과 에러

> error: RPC failed; curl 92 HTTP/2 stream 0 was not closed cleanly: PROTOCOL_ERROR (err 8)
>
> 용량이 커서 생긴 문제였음

1. ```
   git config --global http.version HTTP/1.1
   ```

2. ```
   git config --global http.postBuffer 524288000
   ```

3.  폴더에서 용량 큰거 지우기 -> .git 지우기 -> $git init -> remote 설정 ->$git remote add origin https://github.com/YG-creator/TIL.git -> git add .  -> $git commit -m -> $ git push -u origin master
