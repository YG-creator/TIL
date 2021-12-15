# ID

url : https://www.ncloud.com/nsa/kdtm2
id : class7
pwd : dydrnr1472@





![cloud](md-images/mvc%ED%99%95%EC%9E%A5.PNG)

# Papago



0. 파파고 번역기 naver AI cloud로 구현

    > 1. 로그인
    > 2. 콘솔로 이동
    > 3. Products & Services 이동
    > 4. Application 등록(CLOVA, papago 선택함)



1. service -> cloud -> service

   > 브라우저 일을 service에서 해줘야됨
   >
   > 인증정보에서 clientId, clientSecret 찾아서 입력

```java
public String translate(String words) throws DataAccessException {
		// TODO Auto-generated method stub
		 StringBuffer res = null;
		 String clientId = "opwj8feycx";//애플리케이션 클라이언트 아이디값";
	     String clientSecret = "sPTKEkQY2402Gv1QBWNcjoWrqFWiS9JvR3KMjgB8";//애플리케이션 클라이언트 시크릿값";
	     try {
	         String text = URLEncoder.encode(words, "UTF-8");
	         String apiURL = "https://naveropenapi.apigw.ntruss.com/nmt/v1/translation";
	         URL url = new URL(apiURL);
	         HttpURLConnection con = (HttpURLConnection)url.openConnection();
	         con.setRequestMethod("POST");
	         con.setRequestProperty("X-NCP-APIGW-API-KEY-ID", clientId);
	         con.setRequestProperty("X-NCP-APIGW-API-KEY", clientSecret);
	         // post request
	         String postParams = "source=ko&target=en&text=" + text;
	         con.setDoOutput(true);
	         DataOutputStream wr = new DataOutputStream(con.getOutputStream());
	         wr.writeBytes(postParams);
	         wr.flush();
	         wr.close();
	         int responseCode = con.getResponseCode();
	         BufferedReader br;
	         if(responseCode==200) { // 정상 호출
	             br = new BufferedReader(new InputStreamReader(con.getInputStream()));
	         } else {  // 오류 발생
	             br = new BufferedReader(new InputStreamReader(con.getErrorStream()));
	         }
	         String inputLine;
	         res = new StringBuffer();
	         while ((inputLine = br.readLine()) != null) {
	             res.append(inputLine);
	         }
	         br.close();
	         System.out.println("service "+res.toString());
	     } catch (Exception e) {
	         System.out.println(e);
	     }
		
	
		return res.toString();
	}
```



2. Controller(매핑, response, ModelAndView)

   > /translate 에서 ajax로 response(번역된 영단어) 보냄
   >
   > /view_translate 에서 jsp 보냄

```java
package mc.sn.echo.ai.controller;

import java.io.IOException;

import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.ResponseBody;
import org.springframework.web.servlet.ModelAndView;

import mc.sn.echo.ai.service.AiService;

@Controller("airController")
public class AiContorller {
	@Autowired AiService aiService;
	
	@ResponseBody
	@RequestMapping(value="/translate", method = RequestMethod.GET)
	public void service1(@RequestParam("text") String text,
			HttpServletRequest request, HttpServletResponse response) throws IOException {
		
		request.setCharacterEncoding("utf-8");
		System.out.println(text);
		String result = aiService.translate(text);
		response.setContentType("text/html; charset=UTF-8");
		response.getWriter().print(result);
	}
	
	@RequestMapping(value="/view_translate", method = RequestMethod.GET)
	public ModelAndView login(HttpServletRequest request, HttpServletResponse response) throws IOException {
		ModelAndView mav = new ModelAndView();
		mav.setViewName("service/translate");
		return mav;
	}
	

}

```



3. JSP

   > 번역할 단어를 입력 -> 확인 누르면 js 실행

```java
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Translate</title>
<script type="text/javascript" src="http://code.jquery.com/jquery-latest.js"></script>
<script type="text/javascript" src="resources/js/nmt.js"></script>
<script type="text/javascript">
	function checkResult(){
		temp = {"message":
					{"@type":"response",
					 "@service":"naverservice.nmt.proxy",
					 "@version":"1.0.0",
					 "result":
					 	{"srcLangType":"ko",
						 "tarLangType":"en",
						 "translatedText":"It's a pleasure to meet you."}}}
		alert(temp.message.result.translatedText);
		
	}
</script>
</head>
<body>
<h1>번역페이지</h1>
<form action="" method="get">
	번역할 문장 : <input type="text" name="" id="words">
	<input type="button" value="확인" onclick="sendWords()">
	<input type="button" value="결과확인" onclick="checkResult()">
</form>
번역된 문장 : <span id="message"></span>
<br>
<a href="">index 페이지로 이동</a>
</body>
</html>
```



4. JS(ajax)

   > 번역할 한글 단어를 /echo/translate로 보냄
   >
   > 번역된 영단어를 #message에 표시

```java
/**
 * 
 */
alert('outside jsfile');
function sendWords(){
		words = $('#words').val();
		alert(words); // 1번
		$.ajax({
	         type:"get",
	         url:"/echo/translate",
	         contentType: "application/json",
	         data :{"text":$("#words").val()},
		     success:function (data,textStatus){
		    	  alert(data); // 2번
		    	  resultText = JSON.parse(data);
		    	  text = resultText.message.result.translatedText;
		    	  alert(text); // 3번
		    	  $('#message').text(text);
		     },
		     error:function(data,textStatus){
		        alert("에러가 발생했습니다.");
		     },
		     complete:function(data,textStatus){
		    	 
		     }
		  });
	}
```



# CSR(speech recognition)

1. Controller  

   > jsp 보냄
   >
   > service 결과 반영 jsp 보냄

2. service  

   > ID, secret 입력
   >
   > 바이트로 음성파일 변환 후 cloud에 보냄 -> cloud에서 받아서 문자로 변환

3. jsp

   > 음성파일 업로드 -> contorller로 보냄

4. js

   > ajax

