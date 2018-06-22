## CSS 2.2 기준 수업

### Tree
- 모든 HTML은 Tree 구조
- HTML은 내가 그릴 대상체(structure), CSS가 그릴 디테일(graphics)
- HTML요소는 부모 요소 혹은 자식요소를 가질 수 있다
- 자식 요소를 가질 수 없다면 -> void elements(닫는 태그가 없는 요소들)
  - `<img />` 등등 

### 문법 및 기본 데이터 타입
#### 문법

```css
Basic:

Selector {
  Property-name: property-value;
}


Example 1: p 요소의 색상을 RED로 하고싶은경우

p {
  color: red;
}

Example 2: 잘못된 사례

Bad:

p {
  color: “red”;
}

미리 사전에 정의되어 있는 값 -> 키워드
CSS는 사전에 정의 된 값을 바탕으로 스타일을 입히기 떄문에 미리 정의된 키워드로 사용이 가능
CSS를 사용할 때 가장 많이 하는 행위: 키워드 외우는 것

Basic 2: CSS 대소문자 구분을 할까? 안할까?
답: 매칭 알고리즘을 사용하는 경우에는 대소문자 구분을 하고,
매칭 알고리즘을 사용하지 않는 경우(HTML 태그에 바로 접속)에는 대소문자 구분하지 않음

Basic 3: @rules: CSS에서 특수한 문법을 표현하고자 할 때 사용하는 rule

웹폰트: @font-face
미디어쿼리: @media
애니메이션: @keyframes
다른 CSS 가져오기: @import (비추 -> 이유: 성능저하)

@media (min-width: 360px) {

}

Basic 4: Blocks

여는 중괄호와 닫는 중괄호 내부를 Blocks라고 부른다

Basic 5: Rule set

AS-IS:
h1 { color: red; }
h2 { color: red; }

TO-BE: 

h1, h2 { color: red; }

Basic 6: Declaration(선언)

h1 { color: red; }
h1 { font-size: 16px; }
h1 { line-height: 24px; }

h1 {
  color: red;
  font-size: 16px;
  line-height: 24px;
}

/* 
 * NTS(NHN) 내부의 스타일컨벤션 상 이렇게 작성하라고 권고(지금은 아님)
 * gulp 등의 빌드 혹은 후처리 도구를 사용하여 white-space를 전부 한번에 제거가능
 * 용량이 준다
 */
h1 {color: red;font-size: 16px;line-height: 24px;}

Basic 7: Comment (주석)

개발자에게는 보여야하지만 일반인에게는 보이지 않아도 되는것
나중에 프로덕트 빌드할 때 사라지면 되는 것

```

### 기본 데이터 타입
#### 정수, 실수
- 10진수
- +와 -기호를 사용가능(보통 + 기호는 생략)
- 소수점 사용 가능 

#### Lengths
- `em` -> 해당 요소의 폰트 사이즈에 비례하는 값
- em의 장점: 폰트사이즈에 비례해서 모든 요소들이 늘거나 줄어야할 때 굉장히 유용
- em의 단점: 계산하기가 아주 힘듬
- em은 부모요소와 연관이 있지 않다
```css
p {
  font-size: 14px;
  margin: 1em; (14px)
}


/* em parent example */
body {
  font-size: 12px;
  line-height: 1.8em;
  text-indext: 3em;
}

p {
  font-size: 15px;
  /* 행간(기대): 15 * 1.8 / 실제: 12 * 1.8 */
}

```

- `ex`: 폰트의 x-height 값
- `px`: 1px = 1px
- `in`: 물리단위 = 2.54cm
- `cm`: 센티미터(프린트)
- `mm`: 밀리미터(프린트)
- `pt`: 포인트 -> CSS에서 사용하는 포인트: 1인치의 1/72
- `pc`: 피카사 -> 1pc는 12pt와 동일
- `px`: 0.75pt
  - 100px = 75pt
  - 2592px

#### Percentage
- 상대적단위
- HTML과 동일
- 해당 속성에 따라서 상대적이라는 표현이 달라짐

```css
p {
  font-size: 14px;
  line-height: 120%; /* 폰트 사이즈 기준으로 증가 */
  width: 50% /* 부모 요소의 가로사이즈를 기준 */
}
```
#### URL
- 리소스의 경로
```css
p {
  background: url(“https://example.com”)
}
```

#### 색상
- 해시코드(#FFFFFF, #000000)
  - 해시코드가 앞3자리와 뒤 3자리가 반복되는 경우 생략 가능
    - #000000 -> #000
    - #FFFFFF -> #FFF
- 컬러키워드: black, red, blue 등등..
- rgb 값으로 표현: rgb(255, 255, 255)
  - alpha값도 표현 가능

#### 문자열
```
“문자”
셀렉터[속성값 셀렉터] 사용 시 사용함
가상 요소 셀렉터 -> 이 때도 사용함
URL 에서도 썻음
```

#### CSS 유니코드 지정법
```css
@charset “UTF-8”;
-> 한국어로 주석을 달아도 웹사이트에서 깨져보이지 않음
-> 웹사이트에서 소스코드 보기를 열어서 주석을 열었을 때 깨져보이지 않음.
```

### Selector
- CSS가 HTML개별 요소를 알아내서 스타일을 입힐 수 있게 하는 것

#### 패턴 매칭
- 패턴
- 매칭할 대상

```
TYPE 1: *

Universal Selector : HTML에 존재하는 모든 요소
* {

}

TYPE 2: E(Element)

Type Selector: E 요소와 매치함
E는 아무 요소명으로 변경하여 사용
단점 : 요소가 여러개일 때, 한 요소만 찝어서 스타일을 주는 것이 불가능

E {

}

TYPE 2-1:  p요소에 color:red
p {

}

TYPE 2-2: P요소에 컬러를 레드, 블루

HTML:
<p>얘는 레드</p>
<p>얘는 블루</p>

CSS:
p {
 color:red;
}

TYPE 3: E F

Descendant selectors
특정한 요소 E의 자손요소 F

Type 3-1: div 요소의 자손 요소인 p 요소에 스타일을 넣고싶을 때
HTML: 
<div>
 <p>Hello</p>
</div>

<p>World</p>

p {
 color: red
}

div p {
  color: blue;
}

TYPE 4: E:first-child
첫번째 자식 요소인 E 요소

TYPE 4-1:

HTML:
<div>
 <p>HELL</p>
</div>
<p>WOLRD</p>
<div>
 <p>GOOD</p>
</div>

CSS:
p:first-child {
  color: red;
}

p:last-child {
  color: blue;
}


Type 5: E.classname

Class Selector: 아주 자주 쓰인다 / HTML 요소의 클래스명을 기준으로 CSS를 적용
E는 클래스 셀렉터 / 아이디 셀렉터 / 속성 셀렉터 등에서 생략이 가능하다.
만약 생략할 경우에는 암묵적으로 Universal Selector로써 활용이 됨.

HTML:
<p class="dsc-red">레드</p>
<p class="dsc-blue">블루</p>

CSS:
/* 클래스명을 가지고 있는 어떤(모든) 요소 */
.dsc-red {
  color: red;
}
/* 클래스명을 가지고 있으나 DIV 요소여야만 하는 경우 */
div.dsc-red {
  color: red;
}
.dsc-blue {
 color: blue;
}

Type 6: E#myid
ID Selector
현재 기준으로는 ID 셀렉터를 사용하여 CSS를 넣는 것은 그렇게 추천하지 않는다
ID는 바뀔 가능성이 지배적


Type 7: Pseudo Classes

의사 클래스 -> 존재하지만 요소로써는 존재하지 않는 것

Type 7-1: div에 마우스를 올렸을때
:hover
> 모바일 사파리에서 버그가 있다
> 모바일엔 애초에 마우스가 없음 / 마우스를 올렸다 라는 상태 자체가 존재하지 않음

div:hover {
  background-color: #FAFAFA;
}

Type 7-2: 클릭했을 때
:active
> 클릭했다가 손가락 or 마우스를 때면 원상복귀

div:active {
  background-color: #FAFAFA;
}

유저의 인터렉션: 도구를 이용해서 인터렉션 하게됨
Desktop: 주된 인터렉션 도구: 마우스, 키보드
Mobile: 주된 인터렉션 도구: 터치(손가락)

인지 -> hover(desktop) -> active -> leave(blur) -> out

Type 7-3: 포커스가 갔을때
:focus
- 접근성과 연관이 커서 신경을 써야한다
- outline 부득이한 사정으로 없앴을경우에 focus를 이용한다
```
### Cascading and Inheritance

#### Inheritance
- 특정 요소가 부모 요소의 무언가를 상속받고 싶을 때 사용
```css
Example: input 요소가 부모요소의 font를 상속받고 싶다면.
유용한 이유: 스타일을 한꺼번에 수정할때 유용

input {
  font: inherit;
}

.theme-red {
  color: red;
}

.theme-blue {
  color: blue
}

p {
 color: inherit;
}

부모 요소가 기본적으로 상속해주는 경우: Cascade와 연관성이 큼

body {
  font-size: 18px;
}

body p {
  font-size: /* 18px이 됨*/
}

```

#### Cascade
- 스타일시트(CSS)는 크게 3개의 출처가 있다 (우선순위: 개발자가 작성한 CSS가 다른것보다 최우선 적으로 적용)
  - 작성자(개발자)
  - 유저(폰트 사이즈/폰트 패밀리등을 바꿀 수 있음)
  - 유제 에이전트(UA/유저가 개발자가만든 웹사이트에 접근할 때 사용하는 프로그램)
    - 웹 브라우저
    - 웹뷰

#### 셀렉터 우선순위
- 셀렉터들을 조합해서 사용했을 때, 어떤 CSS가 적용될 것인가에 대한 규칙

> 셀렉터 우선순위 계산법:
  a. HTML에세 style속성을 이용해서 CSS를 넣은 갯수(=a)
  b. ID 셀렉터의 갯수(=b)
  c. Pseudo-class와 다른 셀렉터를 전부(=c)
  d. 요소명과. Pseudo-elements의 갯수(=d)

```css
li	{} /* a=0, b=0, c=0, d=1 -> 0001 */
ul li	{} /* a=0, b=0, c=0, d=2 -> 0002 */
.red	{} /* a=0, b=0, c=1, d=0 -> 0010 */
#red	{} /* a=0, b=1, c=0, d=0 -> 0100 */
<div style=“color: red”> /* a=1, b=0, c=0, d=0 -> 1000 */

li	{}
li	{}  /* 같은 레벨이면 CSS상에서 하단에 있는게 적용 된다*/
```
### Media types
- 유저 에이전트가 어떤 형태의 기기를 사용해서 접근하였는가?
#### 미디어 목록
- `screen`: 화면
- `print`: 인쇄 시
- `tv`: 텔레비
- `projection`: 프로젝터
- `tty`: 지금은 AT(Accessibility Technology)로써 활용되기도 함

```css
@media print {
  /* 프린트 시에만 적용할 CSS */
}

@media (min-width: 480px) {

}
```

### Box model
> **박스**
  웹상에 존재하는 모든 요소들은 사각형 박스로 생겨나는데, 이 사각형 박스를 box-model로 설명하고,
  visual formatting model을 이용해서 화면에 배치됩니다.

#### Box dimension
1. 박스는 컨텐츠 영역을 가지고 있다(컨텐츠 영역 -> 이미지, 텍스트, 등등)
2. 컨텐츠 영역부터 순서대로 padding, border, margin을 가지고 있다

#### padding edge
- 컨텐츠 영역을 감싸고 있는 영역, padding은 가로길이(width) 혹은 세로높이(height)와 직접적으로 연관성을
  가지고 있다. 네 방향의 padding edge가 하나의 padding box를 정의한다.
- 컨텐츠 박스와 border 사이의 영역을 지정하고자 할 때 사용한다.
- 배경이 투명하지 않다
- box에 배경색을 넣어주면 padding영역까지 영향을 받는다.
```css
p {
  padding: 14px;
  /* 위와 같은 형태의 padding 작성법을 축약형 */
  padding-top:14px;
  padding-right:14px;
  padding-bottom:14px;
  padding-left:14px;
  /* 축약형 문법 : 속성별로 달라요 */
  padding: <padding-top> <padding-right> <padding-bottom> <padding-left>
  padding: 14px 15px 17px 12px;
  padding: 14px 20px; /* padding: 14px 20px 14px 20px */
  padding: 14px 20px 17px; /* padding: 14px 20px 17px 20px */
}
```
#### border edge
- border는 외곽선이다
- border는 3가지를 지정해주어야 한다
  - width(선의 굵기)
  - style(선의 형태)
  - color(선의 색생)
- border도 top, right, bottom, left가 존재한다.
```css
p {
  border:1px solid #000000;
  border-top:1px solid #000000;
  border-width: 1px;
  /* 문법 자체는 padding에서 쓰던것과 동일함 */
  border-width: <border-top-width> <border-right-width> <border-bottom-width>
 <border-left-width>
  border-top-width: 1px;
  border-right-width: 1px;
  border-bottom-width: 1px;
  border-left-width: 1px;
  border-style: <border-top-style> <border-right-style> <border-bottom-style>
 <border-left-style>
  border-style: solid;

 border-style: <border-top-color> <border-right-color> <border-bottom-color>
 <border-left-color>
  border-color: #000000;
}
p {
  border-bottom:1px solid #000000;
}
```

#### margin edge
- 배경색의 영향을 받지 않는다(투명)
- 박스와 박스 사이의 간격을 나타낼 때 사용

##### Collapsing margins
> 서로 인접해있는 A요소와 B요소가 존재할 때,
부모 요소인 A요소와 자식 요소인 B요소가 존재할 때,
A요소가 margin-bottom 값을 가지고 있고,
B요소가 margin-top 값을 가지고 있다면,
둘은 서로 병합됩니다 (큰값으로)
```html
<div class="a"></div>
<div class="b"></div>
```
```css
.a {
  margin-bottom: 100px;
}
.b {
  margin-top: 150px;
}
/* 이 때 A와 B 사이 간격은 몇? : 150px */

```
