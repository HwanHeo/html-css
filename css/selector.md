## Selector
>  셀렉터란 무엇인가?
   CSS에서 특정 HTML요소를 가져와 스타일(Style)을 적용시키기 위한 규칙
   특정 HTML  요소를 가져오기 위한 규칙

- 전역 셀렉터 (Universal Selector) 
  - HTML 문서에 존재하는 모든요소
  - 내가 의도하지 않은 요소에도 스타일이 적용될 가능성이 크다
  - CSS의  장점 중 하나인 Cascading을 파괴한다
  - 성능도 좋지 않고, 사용을 비권장 한다.

```
/* box-sizing 속성에 한해서만 Universal Selector를 쓰기도 한다 */
* {
  box-sizing: border-box;
}
```

- 타입 셀렉터(Type Selector)
  - 특정 요소를 가져온다
  - 특정 요소 중에서 필터링 하는게 불가능 하다 

- Class Selector
  - 특정 class 속성 값을 가진 요소
  - 가장 자주 사용된다.

- ID Selector
  - 특정 ID 속성 값을 가진 요소
  - 거의 쓰이지 않는다 (html 자체에 ID를 잘 사용하지 않음)  

- 속성 셀렉터(Attribute Selector)
  - 특정 속성을 가지고 있기만 하더라도 매칭된다
  - 특정 속성의 값의 특정한 문자와 **일치하는** 경우
  - 특정 속성의 값을 공백으로 구문하여 그 중 하나라도 일치하는 경우
  - 특정 속성의 값이 특정 문자로 시작하는 경우
  - 특정 속성의 값이 특정 문자로 끝나는 경우
  - 특정 속성의 값에 특정 문자가 포함만 되어 있어도 된다
  - 특정 속성의 값을 하이픈(-) 단위로 쪼갠 것 중 가장 첫번쨰 것이 해당 값인 것
```
1.
/* 요소[속성명], [속성명] */
HTML:
<input type="text" disabled>

CSS: 
input[disabled] {}
[disabled] {}

2.
HTML:
<input class="input input-search">
<input class="input-search">: 이 요소에만 매칭됨

CSS: 
input[type="text"] {}
input[class="input input-search"] {}

3.
HTML:
<input class="input input-search">
<input class="input-search">

CSS: 
.input-search {}
[class~="input-search"] {}

4.
HTML:
<input class="input">
<input class="input-search">
<input class="input-name">

CSS:
[class^="input]{}

5.
HTML:
<input class="search-area">
<input class="tools-area">
<input class="input-area">

CSS:
[class$="area] {}

6.
HTML:
<input class="around">
<input class="nike are">

CSS:
[class*="ar"] {}

7. 

HTLM: 
<input class="input-area">

CSS:
[class|="input"] {}
```

- 조건 (콤비네이터, 의사 클래스)
  - 특정한 마크업 구조에 맞추어서 css를 입히고 싶을 때 사용하는 것들
  - ~의 자손 요소 (자손과 자식은 다르다)
  - ~의 자식요소 : 자식 콤비네이터
  - 형제 콤비네이터
    - 마크업 순서 상 내 바로 뒤에 있는 형제
    - 마크업 순서 상 내 뒤에 있는 모든 형제
  - 구조 의사 클래스
    - 유저 액션 의사 클래스
       - 마우스를 올렸을때 :hover
       - 포커스가 갔을 때 :focus
       - 클릭했을 때 :active
  - UI 요소 (input)의 상태 의사 클래스
    - UI 요소가 사용 가능한 상태 :enabled
    - UI 요소가 사용 불가능한 상태 :disabled
    - 체크박스 혹은 라디오 버튼이 클릭되어있는 상태 :checked
  - pseudo element (의사 요소)
    - 특정한 요소에 스타일을 위한 HTML이 필요할 때 사용
    - 가상의 HTML을 넣어줘야한다

```
1. 자손
HTML:
<div class="wrap">
    <p>HELLO</p> // 여기에만 반영
    </div>
<p>WORLD</p>

CSS:
.wrap p {
  color: red;
}

2. 자식
HTML:
<div class="wrap">
    <p>HELLO</p> // 자식요소 (여기에만 스타일이 반영)
    <div> // 자식요소
        <p>STUPID</p> // 손자요소 (자손요소)
    </div>
    </div>
    <p>WORLD</p>
</div>

CSS: 
.wrap > p {
  color: red;
}

3-1. 형제
HTML:
<h1>TITLE</h1>
<p>DESC 1</p> // 여기에만 스타일이 반영
<p>DESC 2</p>

CSS:
h1 + p {
  color: red;
}

3-2. 형제
HTML:
<h1>TITLE</h1>
<p>DESC 1</p> // 여기에도 스타일이 반영
<p>DESC 2</p> // 여기에도 스타일이 반영
<h2>BABO</h2>
<p>HELLO</p> // 여기에도 스타일이 반영
<p>HELLO</p> // 여기에도 스타일이 반영
<p>HELLO</p> // 여기에도 스타일이 반영
CSS:
h1 ~ p {
  color: red;
}

4. 구조 의사 클래스
HTML:
<div class="wrapper">
    <div class="row"></div> // :first-child, :nth-child(1), :nth-last-child(5)
    <div class="row"></div> // :nth-child(2), :nth-last-child(4)
    <div class="row"></div> // :nth-child(3), :nth-last-child(3)
    <div class="row"></div> // :nth-child(4), :nth-last-child(2)
    <div class="row"></div> // :last-child, :nth-child(5), :nth-last-child(1)
</div>


CSS:
div:first-child {}
div:last-child {}
div:nth-child(2) {}
div:nth-last-child(2) {}
/*
 * 홀수 차일드
 * 1, 3, 5, 7, 9, 11, 13, ... 번째 자식
 * n은 0부터 시작하여 무한대로 늘어나는 수
 */
div:nth-child(odd) { }
div:nth-child(2n - 1) {}
div:nth-child(2n + 1) {}
/*
 * 짝수 차일드
 */
div:nth-child(even) { }
div:nth-child(2n) { }

/*
 * 특정 조건 중에서 첫번째 자식 :first-of-type
 * 특정 조건 중에서 마지막 자식 :last-of-type
 * 특정 조건 중에서 n번째 자식 : nth-of-type(숫자)
 */
div:first-of-type {}
div:last-of-type {}

5. 유저 액션 의사 클래스
HTML: 
<button type="button">버튼</button>
<input type="text">

CSS:
button:hover {
  background-color: blue;
}

button:active {
  background-color: green;
}

input {
 opacity: 0.3;
 transition: 0.3s opacity;
 outline: none;
}

input:focus {
 opacity: 1;
}

7. pseudo element
HTML:
<div class="row">
  <div style="float:left">레이아웃 1</div>
  <div style="float:left">레이아웃 2</div>
  <div style="clear: both;"></div> // 없어도됨
</div>

<div class="row">
    <div class="contents">여기서부터 콘텐츠</div>
</div>

CSS:
.row::before {
  content:'⭐';
  display:block;
}
.row::after {
  content:'';
  display:block;
  clear:both;
}
```
