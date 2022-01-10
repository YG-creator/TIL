# 경로설정

web.xml에 명시됨(코딩을 위한 환경설정)

jsp 경로 설정 : WEB-INF/spring/appServlet/servlet-context.xml 에 있음

jsp 경로 : WEB-INF/views/

mybatis 와 jdbc 연동 설정: WEB-INF/spring/action-mybatis

jdbc 설정 : WEB-INF/config/jdbc/jdbc.properties  

VO 설정 : resources/mybatis/model/modelConfig

mybatis sql문설정 : main/resources/mybatis/mappers/member.xml

mybatis VO 설정 : main/resources/mybatis/model/modelConfig

js,css,image : webapp/resources에 위치

 

# 사용 이유

> 라이브러리 관리

pom.xml (library 관리)

library 추가 할 때 pom.xml에 추가해야됨 -> library에 자동으로 추가됨

```
<!-- https://mvnrepository.com/artifact/commons-fileupload/commons-fileupload -->
<dependency>
    <groupId>commons-fileupload</groupId>
    <artifactId>commons-fileupload</artifactId>
    <version>1.4</version>
</dependency>
```



# WEB-INF

WEB-INF는 보안성 높음(Controller를 통해서만 접근가능)





encodingFilter(utf-8) - web.xml
