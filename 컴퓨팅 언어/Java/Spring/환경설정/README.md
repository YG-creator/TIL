XML
pom.xml : DI, artifactId
web.xml : container(mybatis), servlet-context, encodingFilter
servlet-context.xml : 요청처리와 아웃풋 처리하는데 필요한 정보(resource, views 정보 위치)
db.properties : 데이터소스 관리(driver,url,username,pwd)
action-mybatis.xml : 커넥션 풀, 쿼리처리(sqlSession)
member.xml : 쿼리자동화
modelCongif.xml : vo정보 위치



# 순서



1. pom.xml 복사  
artifactId 설정
2. web.xml 복사
3. spring - action-mybatis.xml 복사
4. WEB-INF - config 폴더 복사
jdbc properties 설정
5. main - resources - mybatis 폴더 복사
modelConfig.xml 로 VO 설정
member.xml 로 sql 설정  
6. controller 작성
@Controller()
@RequestMapping(value=?, method=Request.?)
함수(@RequestParam("변수") 자료형 변수, HttpServlet request req, ~)
ModelAndView
response.getwriter().print(값)
@Aurto wired service
7. service 작성
@Service()
@Aurtowired dao
8. dao 작성
@Repository
@Aurtowired SqlSession
9. vo 작성
@Component
