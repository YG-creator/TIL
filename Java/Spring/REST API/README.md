# REST

하나의 URI가 고유한 리소스를 처리하는 공통 방식

method 속성의 값에 따라 추가 작업을 요청



# @RestController

controller에 추가



# JSON 라이브러리 추가

pom.xml에 추가



# VO를 json으로 변환

객체 전달 : vo.set~  -> return vo 

객체 리스트 전달 : for {vo.wet} -> return list

map 전달 : vo.set -> map.put(i,vo) -> return map

# VO 추가 구현

toString 구현



# @PathVariable

mapping으로 값을 받음

```java
@RequestMapping(value="/notice/{num}")
public int notice(@PathVariable("num") int num) throws Exception{}}
```



# @RequestBody

JSON 데이터를 VO 객체로 자동 변환

```java
@RequestMapping(~)
public void a(@RequestBody MemberVO vo){}
```



# @ ResponseBody

JSP가 아닌 txt나 JSON으로 결과를 전송

```java
```



# @ResponseEntity

@RestController 예외에 대해 좀 더 세밀한 제어가 필요한 경우 사용