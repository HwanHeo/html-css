## 프로그래밍 언어

### 프로그래밍 종류
- 고급 프로그래밍언어(high level programming language)
  - C, JAVA, C++, HTML, JavaScript
- 저급 프로그래밍언어 (low level programming language)
  - 기계어, 어셈블리

### 해석(고급언어 => 저급언어)
- Compiler
  - 코드 자체를 다 기계어로 해석하여 실행파일을 만듦
  -  컴파일 하다가 에러나면 굉장히 직관적으로 문제 해결이 가능함
- Interpreter
   - 코드를 해석하면서 실행함
   - 장점: 코드가 해석하면서 실행되기 때문에 컴파일 언어보다 직관적
   - 단점: 버그 찾기 힘듬(디버깅)

### Code
- 내가 작성한코드
- 코드를 작성하는 행위: 코딩

## 브라우저
- 웹 브라우저 어플리케이션
- 웹뷰(WebView)
  - 어플리케이션 내에서 뜨는 웹 브라우저
  - 웹 브라우저와 동일하지 않나?
     - 하지만 다름
     - 안드로이드 4.4 미민, Chrome이 기본탑재되지 않은 브라우저는 웹뷰와 기본 브라우저가 서로 다름
     - 삼성 브라우저와 크롬의 동작은 상이함
- 모바일과 데스크탑 브라우저는 또 서로 상이함

### 브라우저와 렌더링
- IE 6 ~ 8 까지의 CSS코드는 chrome, safari, firefox, opera, edge를 지원하는 코드만큼
  필요해서 대응수업은 안함.

### 브라우저의 구조
- 렌더링 엔진
  - 렌더링 엔진: 브라우저에서 렌더링을 수행하는 프로그램
  - 렌더링: 코드를 화면에 보여주기 위한 과정
  - 렌더링 엔진은 브라우저별로 다르다
     - 브라우저별로 같은코드를 다르게 보여줌
  - 렌더링 엔진의 종류
     - Safari => webkit2
     - Chrome, Opera => Blink (웹킷과 아주 유사한 엔진)  
     - Firefox => Gecko (현재 Servo라는 이름의 렌더링 엔진을 제작 중)
     - IE => Trident (비공개)
     - Whale(네이버) => Blink
   - 렌더링 엔진이 동일하다고해서 동작이 100% 동일하진 않음
- 자바스크립트 엔진


## Client & Server
- Client: 고객에게 보여지는 뷰
- Server: 고객에게 자원을 제공하는 공간
- DNS (Domain Name Server)

## HTML
- HTML, Hyper Text Markup Language, Version 5.2
- Markup Language
  - 데이터의 구조를 나타내기 위한 언어
  - Markup Language를 이용하면 문서의 구조를 나타낼 수 있다
     - HTML
- HTML의 목적
  - 문서를 작성하는 것(Document)
  - 웹 어플리케이션도 포함하는 언어(HTML 5.0 ~ 진행형)
- HTML 문법
  - Markup Language
  - tag - less than(<) 기호와 Tag Name 과 grater than(>) 기호로 이루어진 것
  - Element - 여는 태그 <태그명>과 닫는 태그 </태그명>으로 이루어진 것 요소는 
    보통 여는 태그와 닫는 태그로 구성이 되어있습니다
  - Void Element - 다른 컨텐츠를 포함하지 않는 특수한 경우, 닫는 태그 생략이 가능
    ```html
    <img> - 유연한 문법
    <img /> - 엄격한 문법
    ```
  - Attribute - 속성
    ```html
    <div class=“test”></div>
    <div class=‘test’></div>  
    <div class=test></div>  -> 가능하나 잘 사용되지 않음
    ```
    ```html
    // 속성명과 속성값이 같은 경우 
    <input readonly=“readonly” />
    <input readonly /> -> 권장    
    ```
  - White space 가 여러개인 경우 1개만 인식

## ML (Markup Language)
- SGML (Standard General Markup Language)
- XML (eXtensible Markup Language)
- HTML (Hyper Text Markup Language)
  - HTML을 제외한 모든 Markup Language를 Foreign Markup Language
- EmotionML (Emotion Markup Language)
- MathML (Mathmetics Markup Language)


## CSS
- HTML이 문서 자체를 나타낸다면, CSS는 이쁘게 만드는 걸 목표
- Graphics와 관련된 모든 것들을 CSS로 제어
- 레이아웃을 어떡해 그릴것인가?
  - Position
  - Float(레이아웃을 위한 속성X)
- 2017 - CSS3
  - CSS3 -> CSS2.1 을 모듈로 쪼갠 스펙
  - CSS 2.1 (그 안의 하나라도 바꿀라면 문서 전체를 개정)
    - Text
    - Fonts
    - Rendering
    - Selector
  - CSS Text Module Level3
  - CSS Fonts Module Level3

### CSS 문법
1. 문법 
```css
CSS Syntax:
Selector {
  Property: PropertyValue
}
```

2. Selector
   > : CSS는 HTML(XML)을 이쁘게 만들기 위한 언어
      : CSS가 HTML을 알아야함
      : CSS에서 HTML을 아는 수단 -> Selector
      Element Name, Tag Name을 바로 집어서 사용하기도 함.
      CSS는 유연한 언어
      CSS에는 다양한 방법론이 있다(BEM, SMACSS, OOCSS)

**HTML** 
```html
<div>태그의 색상을 레드로 변경한다</div>
```
**CSS** 
```css
div { /* Type Selector */
  Color: red;
}
```

3. Cascading and Inheritance
3.1 Cascading (부모요소에 CSS속성을 지칭했을경우 자식요소도 적용된다)

**HTML**
```html      
<!-- 부모요소 -->
<div>
   <!-- 자식요소 -->
  <p>Example</p>
</div>
```

**CSS**
```css
div {
  color: red;
}
```
3.2 inheritance
     모든 브라우저에서 기본으로 컬러가 지정되있는 태그들은 부모태그(Cascading)에 영향을 받지않아
     inherit으로 지정해줘야 한다

**HTML**
```html         
<!-- 부모요소 -->
<div>
   <!-- 자식요소 -->
  <p>Example</p>
</div>
```

**CSS**
```css
div {
  color: red;
}

a {
  color: inherit;
}
```
