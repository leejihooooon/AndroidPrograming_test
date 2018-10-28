# git 명령어

## 1. 설정과 초기화

### 전역 사용자명/이메일 구성하기
: git config - -global user.name “Your name”

: git config - -global user.email “Your email address”

### 저장소별 사용자명/이메일 구성하기 (해당 저장소 디렉터리로 이동후)
: git config user.name “Your name”

: git config user.email “Your email address”

### 참고로 user 설정이 되어 있지 않으면 Github에 있는 repository에 변경사항을 푸시 한다고 해도 commit count 집계도 안되고 해당 커밋의 작성자 프로필 아이콘도 ? 로 표시되기 때문에 웬만하면 name과 email 주소를 설정하길 추천

### 전역 설정 정보 조회
: git config - -global - -list

### 저장소별 설정 정보 조회
: git config - -list

### Git의 출력결과 색상 활성화하기
: git config - -global color.ui “auto”

### 새로운 저장소 초기화하기
: mkdir /path/newDir

: cd /path/newDir

: git init

### 저장소 복제하기
: git clone <저장소 url>

### 새로운 원격 저장소 추가하기
: git remote add <원격 저장소> <저장소 url>

## 2. 기본적인 사용법

### 아래 명령어에서 [ ]는 선택적인 매개변수를 의미한다.

### 새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기
: git add <파일>

: git commit -m “<메시지>”

### 파일의 일부를 스테이징하기
: git add -p [<파일> [<파일> [기타 파일들…]]]

### add 명령에서 Git 대화 모드를 사용하여 파일 추가하기
: git add -i

### 수정되고 추적되는 파일의 변경 사항 스테이징하기
: git add -u [<경로> [<경로>]]

### 수정되고 추적되는 모든 파일의 변경 사항 커밋하기
: git commit -m “<메시지>” -a

### 작업 트리의 변경 사항 돌려놓기
: git checkout HEAD <파일> [<파일>]

### 커밋되지 않고 스테이징된 변경 사항 재설정하기
: git reset HEAD <파일> [<파일>]

### 마지막 커밋 고치기
: git commit -m “<메시지>” - -amend

### 이전 커밋을 수정하고 커밋 메시지를 재사용하기
: git commit -C HEAD - -amend

## 3. 브랜치

### 지역 브랜치 목록 보기
: git branch

### 원격 브랜치 목록 보기
: git branch -r

### 지역과 원격을 포함한 모든 브랜치 목록 보기
: git branch -a

### 현재 브랜치에서 새로운 브랜치 생성하기
: git branch <새로운 브랜치>

### 다른 브랜치 체크아웃하기
: git checkout <브랜치>

### 현재 브랜치에서 새로운 브랜치 생성하고 체크아웃하기
: git checkout -b <새로운 브랜치>

### 다른 시작 지점에서 브랜치 생성하기
: git branch <새로운 브랜치> <브랜치를 생성할 위치>

### 기존의 브랜치를 새로운 브랜치로 덮어쓰기
: git branch -f <기존 브랜치> [<브랜치를 생성할 위치>]

### 브랜치를 옮기거나 브랜치명 변경하기
: git checkout -m <기존 브랜치> <새로운 브랜치>

### <새로운 브랜치>가 존재하지 않을 경우
: git checkout -M <기존 브랜치> <새로운 브랜치>

### 무조건 덮어쓰기

### 다른 브랜치를 현재 브랜치로 합치기
: git merge <브랜치>

### 커밋하지 않고 합치기
git merge - -no-commit <브랜치>

### 선택하여 합치기
: git cherry-pick <커밋명>

### 커밋하지 않고 선택하여 합치기
: git cherry-pick -n <커밋명>

### 브랜치의 이력을 다른 브랜치에 합치기
: git merge - -squash <브랜치>

### 브랜치 삭제하기
git branch -d <삭제할 브랜치>

### 삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에만
: git branch -D <삭제할 브랜치>

## 4. Git 이력

### 모든 이력 보기
: git log

### 변경 사항을 보여주는 패치와 함께 로그 표시하기
: git log -p

### 1개의 항목만 보이도록 로그 개수 제한하기
: git log -1

### 20개의 항목과 패치만 보이도록 로그 제한하기
: git log -20 -p

### 6개월 동안의 커밋 로그 보기
: git log - -since=”6 hours”

### 이틀 전까지의 커밋 로그 보기
: git log - -before=”2 days”

### HEAD보다 세 개 이전의 커밋 로그 보기
: git log -1 HEAD-3

: git log -1 HEAD^^^

: git log -1 HEAD~1^^

### 두 지점 사이의 커밋 로그 보기
: git log <시작 지점>…<끝 지점>

### 시작 지점이나 끝 지점은 커밋명, 브랜치명, 혹은 태그명이 될 수 있고 조합하여 사용 가능하다.

### 각 항목의 로그 이력 한 줄씩 보기
: git log - -pretty=oneline

### 각 항목마다 영향 받은 줄의 통계 보기
: git log - -stat

### 커밋할 시점의 파일 상태 보기
: git log - -name-status

### 현재 작업 트리와 인덱스의 차이점 보기
: git diff

### 인덱스와 저장소의 차이점 보기
: git diff - -cached

### 작업 트리와 저장소의 차이점 보기
: git diff HEAD

### 작업 트리와 특정 위치 간의 차이점 보기
: git diff <시작 지점>

### 시작 지점은 커밋명 or 브랜치명 or 태그명이다.

### 저장소의 두 지점 사이의 차이점 보기
: git diff <시작 지점> <끝 지점>

### 차이점의 통계 보기
: git diff - -stat <시작 지점> [<끝 지점>]

### 파일의 커밋 정보 줄 단위로 보기
: git blame <파일>

### 파일의 줄 단위의 복사, 붙여 넣기, 이동 정보 보기
: git blame -M <파일>

### 파일의 줄 단위의 이동과 원본 파일 정보 보기
: git blame -C -C <파일>

### 로그에서 복사와 붙여 넣은 정보 보기
: git log -C -C -p -1 <특정 지점>

## 5. 원격 저장소

### 저장소 복제하기
: git clone <저장소>

### 마지막 200개의 커밋만 포함하여 저장소 복제하기
: git clone - -depth 200 <저장소>

### 새로운 원격 저장소 추가하기
: git remote add <원격 저장소> <저장소 url>

### 모든 원격 브랜치 목록 보기
: git branch -r

### 원격 브랜치에서 지역 브랜치 생성하기
: git branch <새로운 브랜치> <원격 브랜치>

### 원격 태그에서 지역 브랜치 생성하기
: git branch <새로운 브랜치> <원격 태그>

### origin 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
: git fetch

### 원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기
: git fetch <원격 저장소>

### 원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
: git pull <원격 저장소>

### origin 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기
: git pull

### 지역 브랜치를 원격 브랜치에 푸싱하기
: git push <원격 저장소> <지역 브랜치>:<원격 브랜치>

### 지역 브랜치를 동일한 이름의 원격 브랜치에 푸싱하기
: git push <원격 저장소> <지역 브랜치>

### 새로운 로컬 브랜치를 원격 저장소에 푸싱하기
: git push <원격 저장소> <지역 브랜치>

### 원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기
: git remote prune <원격 저장소>

### 원격 저장소를 제거하고 관련된 브랜치도 제거하기
: git remote rm <원격 저장소>



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
(3개의 ```또는 ~~~을 사용하여 어떤 언어의 코드인지 명시 할 수 있다.)
~~~

예시)
~~~
```
이것은
코드 블럭
입니다
```
~~~

```
~~~
이것은
코드 블럭
입니다
~~~
```

~~~
~~~C
void f(){
  printf(%s, "이것은 c 코드 입니다.");
}
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
~~~
`인라인 코드 블럭` 
~~~

결과)

`인라인 코드 블럭` 

## 5. 강조 Emphasis

~~~
기울여 쓰기(italic) : ' * ' 또는 ' _ '로 감싼 텍스트 
굵게쓰기(bold) : ' ** ' 또는 ' __ '로 감싼 텍스트 
~~~

예시)
~~~
*기울여쓰기(italic)*

_기울여쓰기(italic)_

**굵게쓰기(bold)**

__굵게쓰기(bold)__
~~~

결과)

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
~~~
---

***

___
~~~

결과)

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
~~~
인라인링크

[Google](http://www.google.co.kr "구글")

참조링크

[Google][1]

[Naver][2]

[1]: http://google.com/ "구글"

[2]: http://naver.com/ "네이버"

url링크

<http://google.com/>

<example@gmail.com/>
~~~


결과)

인라인링크

[Google](http://www.google.co.kr "구글")

참조링크

[Google][1]

[Naver][2]

[1]: http://google.com/ "구글"

[2]: http://naver.com/ "네이버"

url링크

<http://google.com/>

<tlsehdrms124@naver.com/>

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
~~~
1. list item 1
1. list item 2
2. list item 3
0. list item 4
3. list item 5
~~~

결과)

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
~~~

* list item 1
  * list item 1-1
  * list item 1-2
  
+ list item 2
  + list item 2-1
  + list item 2-2
  
- list item 3
  - list item 3-1
  - list item 3-2
~~~

결과)

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

## 9.테이블 Tables

~~~
|기호와 --- 기호를 사용하여 테이블을 만들수있다
( --- 는 반드시 3개 이상이 되어야 구분자로 쓸수있다.)
( | 기호는 생략이 가능하며, 다른 강조문법도 사용가능하다. 또한 : 기호를 통해 정렬방식을 바꿀수있다.)
~~~

### 테이블 생성

예시)
~~~
Header 1 | Header 2
--------- | ---------
Content 1 | Content 3
Content 2 | Content 4
~~~

결과)

Header 1 | Header 2
--------- | ---------
Content 1 | Content 3
Content 2 | Content 4

### 테이블 정렬

예시)
~~~
| Header 1 | Header 2 | Header 3 |
| :-------- | :--------: | --------: |
| Left | Center | Right |
~~~

결과)

| Header 1 | Header 2 | Header 3 |
| :-------- | :--------: | --------: |
| Left | Center | Right |

## 10. 이미지 Adding Images

### 인라인 이미지

예시)
~~~
![alt text](/test.jpg)
~~~

결과)

![favoriteImage1](https://user-images.githubusercontent.com/42789808/47612992-6ace8080-dac9-11e8-813b-eb22cf1055e7.png)

### 링크 이미지

예시)
~~~
![alt text](image_URL)
~~~

결과)

![favoriteImage2](https://postfiles.pstatic.net/20160718_109/cesti5151_1468810958051cvpS5_JPEG/%B1%CD%BF%A9%BF%EE_%B9%CC%B4%CF%BE%F0%C1%EE__%B9%E8%B0%E6%C8%AD%B8%E9_%B0%ED%C8%AD%C1%FA%B7%CE_%C1%F1%B1%E2%BC%BC%BF%E4___%281%29.JPEG?type=w1)

### 참조 이미지

예시)
~~~
![alt text][1]
[1]: /test.png
~~~

결과)

![favoriteImage3][1]
[1]: https://user-images.githubusercontent.com/42789808/47613081-630fdb80-dacb-11e8-8ecb-1b6a0a34168d.jpg

## 11. 라인 분리

~~~
줄바꿈을 하고 싶은때는 Enter키를 2번이상 눌러줘야 한다. 1번 누를시 문장이 이어진다.
~~~

예시)
~~~
enter1
enter2

enter3
~~~

결과)

enter1
enter2

enter3

## 12. HTML코드

~~~
HTML코드를 이용할 수 있다.
~~~

예시)
~~~
<d1>
  <dt>제목</dt>
  <dd>내용</dd>
</dl>
~~~

결과)

<dl>
  <dt>제목</dt>
  <dd>내용</dd>
</dl>
