# Create

## 			테이블 생성

> ​	CREATE TABLE <테이블이름> (<열이름> <데이터타입> <제한>); 

# Read

## 			검색하기 

> ​	SELECT <보고싶은거> FROM <테이블이름> WHERE <조건>;
>
> ​	보고싶은거(*) = all

# Update

## 			테이블 구조 변경

> ​	ALTER TABLE <테이블이름> +

### 					열 삭제

> ​		DROP column <열이름>

### 					열 추가

> ​		ADD <열이름> <데이터타입> <조건>

### 					열 수정

> ​		ALTER COLUMN <열이름> <데이터 타입> <조건>

## 			값 삽입

> ​	INSERT INTO <테이블이름><(열이름(생략가능))> VALUES(<값들>);
>
> ​	주의점 : 테이블 조건에 맞아야됨

## 			값 변경

>​	UPDATE <테이블이름> SET <열이름=값> WHERE <조건>
>
>​	조건에 맞는 행의 열값을 바꿈

# Delete

## 			행 삭제

> ​	DELETE FROM <테이블이름> WHERE <조건>
>
> ​	조건에 맞는 행 삭제

## 			테이블 삭제

> ​	DROP TABLE <테이블이름>



# 데이터 타입

## 			종류

​		NUMBER(a,b) : 전체a자리, 소숫점b자리

​		CHAR(n) : n개 영어글자

​		NCHAR(n) : n개 한글글자

​		VARCHAR2(n) : 최대 n개 영어글자

​		NVARCHAR2(n) : 최대 n개 한글글자

​		CLOB() : Character Long Object

​		BLOB() : Binary Lon Object(영상,이미지)

​		DATE : 연:월:시:분:초

​		TIMESTAMP : 연:월:시:분:초: 밀리초

​		RAWID : 물리적인 primary key

## 		형변환

​		SELECT CAST <열이름> as <데이터타입> FROM <테이블이름>

​		TO_CHAR(), TO_DATE(), TO_NUMBER()

​		보통 DB에서 형변환 안함



# 기타

AS : 열 or table 이름변경

DISTINCT : return unique values
WHERE : 조건
LIKE :	 _ : 한글자	 / 	% : 한글자 이상
BETWEEN a and b: a이상 b이하
AND and OR : 여러개 조건
ORDER BY : 정렬
LIMIT(시작점,갯수) :  갯수 제한
CASE : 조건문

```sql
CASE <열이름> WHEN <조건> THEN <결과값>
             WHEN <조건> THEN <결과값>
             .......
 			ELSE <결과값>
END
```

COUNT(): 행 수 세기
SUM(): 합
MAX()/MIN(): 최댓값,최솟값
AVG(): 평균
ROUND(열, n): 소숫점 n번째 까지 반올림



# Join

## 		개념 

​		CRUD 편의를 위해  테이블 합치기

## 		종류

​		1. INNER JOIN : 교집합만 합치기  // 중요 

```sql
	SELECT ~ FROM <테이블이름1> INNER JOIN <테이블이름2> on <join될 조건>
```

​		2. OUTER JOIN : join될 조건 만족하지 않는 행까지도 포함    // 중요

​			* LEFT OUTER JOIN : 왼쪽거 기준 합치기 

​			* RIGHT OUTER JOIN : 오른쪽거 기준 합치기 

  ```sql 
  	SELECT ~ FROM <테이블이름1> LEFT OUTER JOIN <테이블이름2> ON <join될 조건>
  ```

​		3. FULL OUTER JOIN : 합집합(중복제거)

```sql
	(LEFT JOIN) UNION (RIGHT JOIN)
```

​		4. CROSS JOIN : 모든 조합

​		5. EXCLUSIVE LEFT JOIN : LEFT 차집합

```sql
	SELECT ~ FROM a LEFT JOIN b ON a.c = b.d  WHERE b.d is NULL
```

​		6. SELF JOIN

```sql
	SELECT ~ FROM <테이블이름1> <이름1> INNER JOIN <테이블이름1> <이름2> ON <Join될 조건>
```

