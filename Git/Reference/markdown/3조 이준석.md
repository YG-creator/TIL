# Markdown 정리

----



## Heading

#의 개수에 따라 h1~h6까지 표현 가능

문서 구조를 위한것이니 글자 크기 조절로는X



## List

순서가 있는 리스트 (ol)

순서가 없는 리스트(ul)

Tip) 

tab-하위 항목 shift+tab-상위 항목



## Fenced Code block

코드 블록은 backtick 기호(1옆에 있는키) 3개로 작성

코드 블록에 특정 언어 명시하면 Syntax Highlighting(각 언어마다의 글자색?) 적용 가능(일부 환경은 안될 수 있음)

ex)

````
```json

코드

```
````



## Inline Code block

코드 블록은 backtick 기호 1개를 인라인에 활용하여 작성(`

Inline Code는 Fenced Code block처럼 문법 색이 칠해지지 않음



## Link

``` [문자열](url)을 통해 링크 작성 가능 ```

**주의사항**      [구글]띄어쓰기X(링크)

특정파일들 포함하여 연결 시킬 수도 있음



## Image

``` ![문자열](url)을 통해 이미를 사용 가능 ```

특정파일들 포함하여 연결 시킬 수도 있음



## Blockquotes (인용문)

``` >를 통해 인용문을 작성``` 



## Table (표)

일부 지원 안되는 환경도 있음

ctrl + t로 생성 가능



## text 강조

굵게(bold)

``` **bold**, __bold__``` 



기울임(ltalic)

```*ltalic, ltalic*, _ltalic, ltalic_```



## 수평선

3개 이상의 asterisks (***), dashes (---), underscores (___)



## 주석

각 언어의 주석 방식쓰면됨

//자바

#파이썬

-- SQL