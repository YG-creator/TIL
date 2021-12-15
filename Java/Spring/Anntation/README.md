# 개념

java 내에 작성하여 DI 작업을 자동으로 하게함 (XML에서 ref를 참고해서 bean을 만드는 과정을 쉽게함)



# 종류

1. @Controller : Controller로 설정

2. @Service : Service로 설정

3. @Repository : DAO로 설정

4. @Component : VO로 설정

5. @Autowired : Controller - Service - DAO - VO - sqlSession연결

   * Controller

     ```java
     @Controller("memberController")
     public class MemberControllerImpl   implements MemberController {
     	@Autowired
     	private MemberService memberService;
     	@Autowired
     	private MemberVO memberVO ;
     ```

   * Service

     ```java
     @Service("memberService")
     @Transactional(propagation = Propagation.REQUIRED)
     public class MemberServiceImpl implements MemberService {
     	@Autowired
     	private MemberDAO memberDAO;
     ```

   * DAO

     ```java
     @Repository("memberDAO")
     public class MemberDAOImpl implements MemberDAO {
     	@Autowired
     	private SqlSession sqlSession;
     ```

   * VO

     ```java
     @Component("memberVO")
     ```

     

6. @RequestMapping(value="주소", method=RequestMethod.GET or POST)

   * Controller

     ```java
     ```

     

# 바인딩

1. @RequestParam

* request의 변수 -> 변수에 삽입 

  ```java
  메소드 매개변수에 @RequestParam("userID") String userID 선언한 후
  System.out.println(userID) -> userID출력됨
  ```

* required : True 이면 null일때 예외발생  /  False이면 null로 출력

* Map : 직접 변수에 값 삽입 필요 없이 자동으로 삽입됨

  ```java
  메소드 매개변수에 @RequestParam Map<String,String> info 선언한 후
  System.out.println(info.get("userID")) -> userID 출력됨
  ```

2. @ModelAttribute : request 변수 -> VO에 매개변수 값에 삽입

```java 
메소드 매개변수에 @ModelAttribute("info") LoginVO loginVO 선언한 후
System.out.println(loginVO.getUserId()); -> info.userID가 출력됨
```

3. Model

```java
메소드 매개변수에 Model model 선언후에
model.addAttribute("키","값")
```



# CRUD

Add

```java
@Override
@RequestMapping(value="/member/addMember.do" ,method = RequestMethod.POST)
	public ModelAndView addMember(@ModelAttribute("member") MemberVO member,
			                  HttpServletRequest request, HttpServletResponse response) throws Exception {
		request.setCharacterEncoding("utf-8");
		int result = 0;
		result = memberService.addMember(member);
		ModelAndView mav = new ModelAndView("redirect:/member/listMembers.do");
		return mav;
	}
```



Read

```java
@Override
	@RequestMapping(value="/member/listMembers.do" ,method = RequestMethod.GET)
	public ModelAndView listMembers(HttpServletRequest request, HttpServletResponse response) throws Exception {
		String viewName = getViewName(request);
		List membersList = memberService.listMembers();
		ModelAndView mav = new ModelAndView(viewName);
		mav.addObject("membersList", membersList);
		return mav;
	}
```



Delete

```java
@Override
	@RequestMapping(value="/member/removeMember.do" ,method = RequestMethod.GET)
	public ModelAndView removeMember(@RequestParam("id") String id, 
			           HttpServletRequest request, HttpServletResponse response) throws Exception{
		request.setCharacterEncoding("utf-8");
		memberService.removeMember(id);
		ModelAndView mav = new ModelAndView("redirect:/member/listMembers.do");
		return mav;
	}
```





ModelAndView mav = new ModelAndView("경로") ->  ModelAndView 생성

mav.addObject	:  바인딩

mav.setViewName("뷰이름") : View 설정

return mav : 전달

