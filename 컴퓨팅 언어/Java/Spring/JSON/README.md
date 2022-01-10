# 형식

resEntity = new ResponseEntity(객체, Http상태)

return resEntity

```java
@RequestMapping(value = "/{articleNO}", method = RequestMethod.GET)
	public ResponseEntity<ArticleVO> findArticle (@PathVariable("articleNO") Integer articleNO) {
		logger.info("findArticle 메서드 호출");
		ArticleVO vo = new ArticleVO();
		vo.setArticleNO(articleNO);
		vo.setWriter("홍길동");
		vo.setTitle("안녕하세요");
		vo.setContent("홍길동 글입니다");
		return new ResponseEntity(vo,HttpStatus.OK);
	}	
```



# js

JSON.stringify(data) : 자바의 객체를 string으로 변환

JSON.parse(temp) : 객체로 변환

객체.writer() : string으로 출력

restfull 장점 : url이 같아도 type이 다르면 다른결과가 나올수있음