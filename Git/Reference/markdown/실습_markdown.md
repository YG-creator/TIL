# 마크다운 문법

## Heading

문서의 제목이나 소제목으로 사용.

- #의 개수에 따라 대응되는 수준(Heading level)이 있으며, h1~h6까지 표현 가능
- 문서의 구조를 위해 작성되며 글자 크기를 조절하기 위해 사용되어서는 안됨

## LIst

순서가 있는 리스트(ol)와 순서가 없는 리스트(ul)로 구성.

- 예시

## Fenced Code block

- 코드 블록은 backtick 기호 3개를 활용하여 작성(''' ''')

- 코드 블록에 특정 언어를 명시하면 Syntax Highlighting 적용 가능

- 예시

  ``` java
  ```java
  {
    String st1 = "Hello";
    String st2 = "java";
    System.out.println(st1 + st2); //Hello java
  }
  ```

## Inline Code block

코드 블록은 backpack 기호 1개를 인라인에 활용하여 작성(``)

- 예시

  ```
  At the command prompt, type 'nano'
  ```

  At the command prompt, type `nano`.

	## Link

[문자열] (url) 을 통해 링크를 작성 가능.

- 예시

  ``` 
  My favorite search engine is [Google](https://google.com).
  ```

  My favorite search engine is [google](https://google.com).

### Image

