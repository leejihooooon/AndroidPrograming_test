# 마크다운 문법

## 1. 제목 Headers

~~~
#으로 시작하는 텍스트 
#은 하나부터 여섯개까지 쓸 수 있고, #이 늘어날때마다 제목의 수준은 내려간다. 
(보통 글씨 크기가 작아진다.)
또는 - , = 을 이용하여 h1, h2를 쓸 수 있다. 
~~~

예시) 
~~~
# h1
## h2
### h3
#### h4
##### h5
###### h6
h1
===
h2
--
~~~

결과)

# h1

## h2

### h3

#### h4

##### h5

###### h6

h1
===

h2
--

## 2. 인용 Blockquotes

~~~
>으로 시작하는 텍스트 
~~~

예시)
~~~
>This is a first blockqute.
>>This is a second blockqute.
>>>This is a third blockqute.
~~~

결과)
>This is a first blockqute.
>>This is a second blockqute.
>>>This is a third blockqute.


## 3. 코드 블럭 Code Blocks

~~~
```  혹은  ~~~  코드 첫 줄과 마지막 줄에 Back quote (')또는 물결(~) 3개 삽입 
~~~

예시)
~~~
```
이것은
코드 블럭
입니다
```
~~~
이것은
코드 블럭
입니다
~~~
~~~C
void f(){
  printf(%s, "이것은 c 코드 입니다.");
}
~~~
~~~

결과)

```
이것은
코드 블럭
입니다
```
~~~
이것은
코드 블럭
입니다
~~~

~~~C
void f(){
  printf(%s, "이것은 c 코드 입니다.");
}
~~~

## 4. 인라인 코드 Inline Code Blocks
~~~
`(Back quote) ' 로 감싸진 텍스트 
~~~

예시)

`인라인 코드 블럭` 

## 5. 강조 Emphasis

~~~
기울여 쓰기(italic) : ' * ' 또는 ' _ '로 감싼 텍스트 
굵게쓰기(bold) : ' ** ' 또는 ' __ '로 감싼 텍스트 
~~~

예시)

*기울여쓰기(italic)*

_기울여쓰기(italic)_

**굵게쓰기(bold)**

__굵게쓰기(bold)__

## 6. 수평선 Horizontal Rules

~~~
- 또는 * 또는 _을 3개 이상 작성 
(단, '-'을 사용 할 경우 header로 인식할 수 있으니 이 전 라인은 비워 두어야 한다.) 
~~~

예시)

---

***

___

## 7. 링크 Links

### 외부 링크 External Links

~~~
[링크](http://example.com "링크 제목") 인라인 링크 

[링크1][1] [1]: http://example1.com1/ "링크제목1" 참조링크

<example.com/> <example@example.com> url링크
~~~

예시)

인라인링크

[Google](http://www.google.co.kr"구글")

참조링크

[Google][1]

[Naver][2]

[1]:http://google.com/"구글"

[2]:http://naver.com/"네이버"

url링크

<http://google.com/>

<example@gmail.com/>

### 내부 링크 Internal (Anchored) Links

~~~
[링크](#id) 내부링크
~~~

## 8. 리스트 Lists

### 순서 있는 리스트 Ordered Lists

~~~
숫자 다음.을 찍는다. (적힌 숫자랑 상관없이 순서대로 번호가 매겨진다.)
~~~

예시)

1. list item 1
1. list item 2
2. list item 3
0. list item 4
3. list item 5

### 순서 없는 리스트 Unordered Lists

~~~
* , + , - 으로 시작
~~~

예시)

* list item 1
  * list item 1-1
  * list item 1-2
  
+ list item 2
  + list item 2-1
  + list item 2-2
  
- list item 3
  - list item 3-1
  - list item 3-2
  - list item 3-3

