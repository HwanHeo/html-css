## 공통 인프라구조
### 공백문자 (white space)
- U+0020 SPACE
- U+0009 CHARACTER TABULATION (tab)
- U+000A LINE FEED (LF)
- U+000C FORM FEED (FF)
- U+000D CARRIAGE RETURN (CR)
### ASCII 대문자 
- U+0041 LATIN CAPITAL LETTER A ~
- U+005A LATIN CAPITAL LETTER Z
### ASCII 소문자 
- U+0061 LATIN SMALL LETTER A ~
- U+007A LATIN SMALL LETTER Z
### ASCII 숫자 
- U+0030 DIGIT ZERO (0) ~
- U+0039 DIGIT NINE (9)
### ASCII 16진수 
- U+0030 DIGIT ZERO (0) ~
- U+0039 DIGIT NINE (9),
- U+0041 LATIN CAPITAL LETTER A ~
- U+005A LATIN CAPITAL LETTER Z,
- U+0061 LATIN SMALL LETTER A ~
- U+007A LATIN SMALL LETTER Z
```
1 2 3 4 5 6 7 8 9 A B C D E F
Color: HEX
16진수 6개로 이루어진 컬러 표현방법
#000000
#FFFFFF
```

### 불리언 속성
일부 속성은 불리언(참과 거짓) 속성이다. 이 때는 다른 언어처럼 true, false로 표현하지 않고 속성이 존재
하면 true, 존재하지 않으면 false로 표현한다.

```
EXAMPLE :
입력(input)을 받고싶지 않을(disabled) 때

1. disabled 속성이 true 이므로 이 input은 사용 불가하다.
<input disabled />

2. disabled 속성이 true 이므로 이 input은 사용 불가하다.
<input disabled="disabled" />

3. 만약 다시 입력받고싶다면 diabled 속성을 제거한다
<input />

```

### 숫자
- 정수 (Signed integers)
- 양수 (Non-negative integers)
- 실수 (Floating-point numbers)
- 퍼센테이지와 길이 (Percentages and lengths)
   - 0% ~ 100%
   - 퍼센테이지 => 상대값
   - 최소 0, 최대 300 => 100% = 300 => -100% = -300
   - 모바일 작업, 해상도에 따라 사이즈가 변경되어야 할 때
- 0이 아닌 퍼센테이지와 길이 (Non-zero percentages and lengths)
- 실수 목록 (Lists of floating-point numbers)
- 좌표 목록 (Lists of dimensions)

## Element

### Basics

```
EXAMPLE:

Tag: <태그명></태그명>
Open Tag: <태그명>
Close Tag: <태그명>
Elements: <div></div>, HTMLDivElement (Javascript)
Attributes: <div class=“hello”>안뇽</div>
Boolean Attributes: <input disabled />, 등등
Attribute Value: 항상문자열 (“”, ‘’)
<div class=hello></div> -> 권장하지않음

```

### Semantics

> HTML은 문서를 작성하기 위한 언어다.
HTML 5.2 스펙에서 정의하는 HTML 내의 요소(Elements), 속성(Attribute) 및 속성 값(Attribute
value)들은 특정한 의미를 가지고 있으며, 이를 semantics라고 부른다. 예를 들어 ol 요소는 순서 있는
목록을 의미하고 lang 속성은 콘텐츠의 언어를 의미한다
이 정의는 웹 브라우저, 검색 엔진과 같은 HTML 프로세서에서 허용하며 이는 부모 문서 및 어플리케이션에
따라 다른 컨텍스트로 제공한다.
다른 컨텍스트의 예시로 article 이란 요소를 예로 들 수 있으며, 이 요소는 문서 의미로 사용될 때는 주로
다른 콘텐츠와 독립적인 콘텐츠 로써 사용되지만 어플리케이션 의미로 사용될 때는 Widget 같은 의미로써
사용된다.

### Element Definition
- 각 요소는 아래 목록의 정보를 포함하고 있습니다.
- 카테고리
  - 요소의 하위 요소 및 하위 요소로 포함되어야 하는 것의 일반적 설명
  - 카테고리를 다 외우는 것은 불가능에 가깝다.
  - HTML 유효성 검사기(Validator)
- 이 요소를 사용할 수 있는 컨텍스트
  - 이 요소를 어디서 사용할 수 있는가에 대한 정보. 이 정보는 이 요소를 자식으로 허용하는 요소의 컨텐츠 모델과 중복되며 편의상 제공됩니다.
- 컨텐츠 모델
- HTML에서 태그 생략
 - 닫는 태그가 생략 가능한지..
 - 닫는 태그 생략을 안하는 걸 권장.
- 컨텐츠 속성

### Content Model
> 컨텐츠 모델이란 이요소가 가지고 있는(가질 수 있는) 컨텐츠의 형태이다
  이 요소의 컨텐츠가 어떤걸 향해있는지 -> 컨텐츠 모델
  Contents: 텍스트, 이미지, 비디오 등등 HTML내에서 *작성자가 표형하고 싶은 모든 것*

### Metadata
- 로봇에게 전해주고 싶은 모든것
```
<base>, <link>, <meta>, <noscript>, 
<script>, <style>, <template>, <title>
```

### Flow
 - Body 요소 안에 있는 모든 요소(유저에게 보이는 거의 모든 요소)

### Sectioning
- Section, Heading과 Footer의 범위(Scope)를 지정하기도 합니다(outline과 연관성이 있음)
```
<article>, <aside>, <nav>, <section>
```

### Heading
- 섹션의 제목, 1이 가장 큰 제목(대제목)/6이 가장 작은 제목(소제목)

```
<h1> ~ <h6>
```

### Embedded
> 외부에서 가져오는 모든 것(HTML이 아닌 것)을 말한다
   Embedded Content는 거의 대부분 Fallback 요소를 가질 수 있다.

```
<img>, <audio>, <video>, <picture>, <svg>, <iframe>, <canvas>
<embed>, <object>, <math>
```

### Phrasing Content
- 문서의 텍스트 레벨의 요소를 전부 포함하고 있음.
  
### Interactive
> 유저와 상호작용하는 모든요소
  (유저가 무언가를 할수있는 있다)

```
<a>, <audio>, <button>, <details>, <embed>, <iframe>,
<img>, <input>, <label>, <select>, <textarea>, <video>
```

### Palpable
- 내부에 Flow 컨텐츠 혹은 Phrasing 컨텐츠를 허용하는 모든 컨텐츠 (하나 이상의 컨텐츠를 포함하고 있는)

### Script-supporting
- **스크립트** 를 지원하는 모든 요소 / 자기 스스로 무언가를 렌더링 하지는 않음

### Global Attributes
#### 모든 요소들에서 사용할 수 있는 속성
 - class
 - id
 - contextmenu -> menu(지원하는 브라우저가 firefox만 지원
 - title
```
<a href=“https://naver.com” target=“_blank” title=“새창으로 이동”>네이버</a>
```
 - lang
   - 이 요소의 언어
   - 한국어: "ko"
   - 일본어: "ja"
   - 영어: "en", "en-US", "en-UK"
   - 중국어: "zh"
 - translate
   - 불리언
   - 이 요소를 번역한 건지 안할 건지
   - translate 속성값을 "no"로 주면 내부 컨텐츠를 번역하지 않는다.
 - dir
 - style
   - CSS를 INLINE으로 넣을 떄 사용
   - 권장하지 않음 (유지보수 힘듬)
   - 불리언
 - draggable
   - value true, false
   - 요소를 드래그를 가능하게 해줌
   - dropzone -> 드래그 앤 드랍

#### Class와 ID
- ID: Identifier(식별자)/ 이 요소가 어떤 것인지 식별할 수 있게(Unique) 한번말 사용할 수 있다(중복 불가)
```
<!—- 사용불가 —>
<div id=“warp></div>

<div id=“warp></div>
```
- Class: 중복가능, 연속된 값을 넣는 것도 가능

- Unique, Not Unique의 차이

## The Elements of HTML

### Document Element[1]
- `<html>`
  - 문서의 HTML을 나타낸다.
  - 모든 HTML 요소의 Root Element로 활용이 된다
  - Root: 특정 프로그램에서 가장 기반이 되는 객체 혹은 요소를 Root라고 지칭을 한다
  - html 요소에 lang 속성을 정의하면 접근성에 좋다(접근성 지침에 있음)

### Document metadata[6]
> Metadata Content에 속하는 아이들

- `<head>`
  - 로봇에게 전달할 컨텐츠를 포함하는 부모
- `<title>`
  - 이 페이지의 제목
  - `<head>` 요소의 자식요소로만 사용가능
- `<base>` -> 잘사용 하지 않는다
  - 피싱사이트를 만들 때 많이 사용함.
  - Path를 속인다
- `<link>`
  - 리소스(css, favicon)와 이 HTML페이지를 연결 해준다.
- `<meta>`
  - 메타데이터를 표현하기 위한 요소
  - 메타데이터: 다른 데이터를 설명하는 데이터
  - attribute
    - charset -> 이 사이트에서 사용되는 유니코드 문자열을 지정
      - 지정해 주지 않으면 영어권이 아닌 언어는 폰트가 깨질 수 있다
    - og:title -> 페이스북에 공유할 때 사용할 타이틀
    - og:description -> 페이스북에 공유할 때 사용할 설명
    - og:img -> 페이스북에 공유할 때 사용할 이미지
    - og:url -> 페이스북에 공유할 때 사용할 URL

- `<style>`
  - CSS를 해당 HTML페이지 내에서 작성할 수 있게 하는 요소


### Sections[13]
> 사전지식: 아웃라인(outline)
  아웃라인: 출판용어(편집용어), 개요/대강/기안
  여러 컨텐츠들이 한 섹션안에 감싸져 있을때, 이문서 전체의 개요(아웃라인을 그리는것)

- 로봇: 검색엔진, 브라우저, 크롤러(사이트를 돌아다니면서 데이터를 긁어가는 로봇)같은 것들
- 유저: 사용자, 사이트에 방문해 이용하는 사람
- 접근성: 스크린 리더와 같은 Assistant Technology(AT)가 접근 가능하게 하는것
- HTML을 잘 작성한다 -> 로봇이 잘 이해할 수 있게 한다

- `<body>`
  - HTML 내에서 유저(사용자)에게 보이는 모든 것들
  - `<body>` 안에 없는 것들은 유저에게 보이지 않는 것들이 더 많다.
  - `<body>` 에는 기본적으로 margin: 8px 이 들어가 있다(표준)
- `<article>`
  - `<article>` 요소는 자기 자신만으로도 완벽한 컨텐츠를 나타낼 때 사용한다.
  - 매거진, 뉴스 등의 개별 Article들
  - Article에도 반드시 제목이 필요함
- `<section>`
  - 문서 내에서 일반적인 섹션
  - 제목을 붙일 수 있는 컨텐츠 블록
  - 제목을 붙일 수 없는 컨텐츠 블록 -> “<div>” 같은 걸로 처리
- `<nav>`
  - 네비게이션
  - 유저가 탐색할 수 있게하는 무언가
- `<aside>`
  - 본문의 내용을 꾸미는데 이 내용을 봐도 되고 안봐도 되는것

- `<h1> ~ <h6>`
  - 섹션의 제목
  - h1 가장 큰 제목, 한 페이지 내에서 1번만 사용
    - 한 사이트의 제목/이 콘텐츠의 제목
  - h1부터 h6까지 반드시 1단계씩 내려가야 함.
- `<header>`
  - 메인 컨텐츠 내에서 컨텐츠를 시작해주는 요소
  - `<header>` 중첩가능 (HTML 5.2부터)
- `<footer>`
  - 컨텐츠를 끝내는 요소
  - `<footer>` 중첩가능 (HTML 5.2부터)

### Grouping content [15]
- `<p>`
  - 문장 (끝)
- `<address>`
  - 실제 주소 -> 이 웹사이트를 운영하는 사람의 실제 주소
  - 이 웹사이트의 운영주체와 만날 수 있는 무언가를 제공할 때
- `<hr>` -> horizontal rule
  - 문맥 커터 (자주 쓰이진 않음)
- `<pre>` -> preformatted text
  - 작성한 그대로 화면에 뿌려주는 역할
  - 코드 작성한 것을 직접적으로 보여주고 싶을 때 많이 사용
- `<blockquote>`
  - 인용문
  - `<cite>` -> 출처
```
<blockquote cite="http://news.topstarnews.net/detail.php?number=291654">알토란’"
‘알토란’에서 무더위를 이기는 밥상을 소개했다. 최근 MBN... 한편 임성근 조리기능장은 불 앞에 오래 서
있기 힘든 주부들을 위한 여름용 ‘만능 비빔장’을 소개했다. 이 비빔장 <cite>위키백과</cite> </
blockquote>
```
- `<ol>`
  - 순서 있는 목록 -> Ordered List
  - 자식요소로는 `<li>` 요소만 가질 수 있다
  - `<li>`
     - 리스트 아이템
- `<ul>`
  - 순서 없는 목록 -> unordered List
  - 자식요소로는 `<li>` 요소만 가질 수 있다
  - `<li>`
     - 리스트 아이템
- `<dl>`
   - 정의 목록 (Definition List)
   - 설명하고자 하는 대상(dt)이 있고 그걸 설명하는 콘텐츠(dd)로 이루어진 것
  - 자식요소로는 `<dt>`, `<dd>` 요소만 가질 수 있다
   - `<dt>` -> Definition Term
      - 설명하고자하는 대상
   - `<dd>` -> Definition Description
       - 설명하고자하는 내용
- `<figure>`
   - 콘텐츠를 포함하고 있는 설명
   - 본문에 있는 내용을 부가적으로 설명하고, 그 때 컨텐츠(텍스트, 테이블, 코드, 이미지)를 가지고 있는
      경우 `figure` 를 이용해 표현합니다.
   - `<figcaption>`
      - 설명
```
<figure>
  <img src="choeun.jpg" alt="" />
  <figcaption>그림 1. 강아지가 밥을 먹고있다</figcaption>
</figure>
<figure>
  <figcaption>코드 1. x 라는 요소를 JS를 이용해 가져오고 있다</figcaption>
  <pre><code>var x = document.querySelector('x')</code></pre>
</figure>
```
- `<main>`
   - 이 페이지의 메인 콘텐츠
   - 한 페이지 내에서 main 은 여러개 쓰일 수 있으나 (HTML 5.2) 하나만 노출되어야 함
```
잘못된 용법:
<main>메인 1</main>
<main>메인 2</main>
<main>메인 3</main>

<!-- 네이버 모바일 홈 예제 -->
바른 용법:
<main>메인 1</main>
<main hidden>메인 2</main>
<main hidden>메인 3</main>
```

- `<div>`
   - 특별히 의미가 없는 요소
   - CSS를 반영하여야 하나 마땅히 사용할만한 요소가 없을 때 div 를 사용
   - 컨텐츠를 그룹해서 그 컨텐츠에 무언가 영향을 주고 싶을 때
```
<article lang="ko">
  안녕 친구들, 만나서 반가워
  <div lang="en">
    Hello everyone, Nice to meet you
  </div>
</article>
```

### Text-level semantics [30]
- 다 텍스트로 취급되는 요소들

- `<a>`
  - 하이퍼 링크 (특정한 위치로 이동시키는 링크)
  - href
    - href 속성이 존재해야지만 이 요소가 하이퍼링크로써 동작을 하게 됨.
    - 하이퍼링크 (Path)
      - Hash Link ( # ) / 프론트엔드개발 (React, Angular)을 하시면 Hash를 이용해서 Router
        를 구축하기도 함.
      - 링크 ( https://naver.com )
      - 본인의 사이트 내를 탐색할 때는 Path/File
  - Conditional Link (특정한 상황에서만 링크가 활성화되었으면 좋겠을 때)
      - 이 때 href 속성을 Toggle 함으로써 요소의 링크를 활성화시키거나 비활성화시키기도 함
- `<em>`
  - 강조 : 다른 텍스트보다 좀 더 중요함
  - `<p>고양이는 개보다 귀엽다</p>`
  -  `<p><em>고양이</em>는 개보다 귀엽다</p>`
- `<strong>`
  - 미친 강조 : 아주 중요하고, 심각한 내용을 다루고, 경고에 가까운 수준
  -  `<p><strong>고양이</strong>는 개보다 귀엽다</p>`
- `<small>`
  - 덜 강조되는 콘텐츠
  - `<p>$15 <smal>VAT 별도</small></p>`
- `<s>`
  - 더 이상 사용 되지 않는 콘텐츠 (쇼핑몰에서 할인정보 표현)
  - `<p><s>Juice: $5</s></p>`
  - `<p><strong>Now Juice is $3</strong></p>`
- `<cite>`
  - 출처
- `<q>`
  - 인용, 인용구
  - `<q cite="URL">사람은 그가 입은 제복대로의 인간이 된다</q>`
- `<dfn>`
  - 이 페이지 내에서 정의하는 용어
  - `<dfn title=“Hyper Text Markup Language”>HTML</dfn>`
- `<abbr>`
  - 약자
  - `<dfn><abbr title=“Hyper Text Markup Language”>HTML</abbr></dfn>`
  - `<abbr title=“버스정류장”>버정</abbr>`
- `<ruby>`
  - `<rb>` -> 설명하고자 하는 베이스
  - `<rt>` -> 설명하고자 하는 내용
  - `<rtc>` ->  아래쪽에 설명하고자 하는 내용을 넣고싶을 때
  - `<rp>` ->  괄호, 콘텐츠에 포함은 안되지만 꾸밈말을 쓰고싶을 때
- `<data>`
  - 데이터를 표현하는 HTML 요소
  - 인간이 읽기 위한 건 아니고 기계를 위한 데이터

- `<time>`
  - 시간
    - `<time>2017-08-19</time>` -> 원래 포맷 O
    - `<time datetime="2017-08-19">2017.08.19</time>` -> 그냥 쓰면 X, datetime 속성을 이용하여 포맷에 맞는 시간을 보여주어야 함
  - datetime
    - time 요소 내에서 다른 포맷의 콘텐츠를 사용하고 싶을 때,
    - datetime 속성을 이용해서 원래 포맷의 시간을 나타냄
- `<code>`
  - 유저가 작성한 코드
- `<var>`
  - 명시적 변수 (자바스크립트 등의 언어의 변수)
- `<samp>`
  - 특정한 코드가 있을 때, 그 코드의 결과값으로 기대할 수 있는 무언가
  - `<pre><samp>3</samp><code>1+2=?</code></pre>`
- `<kbd>`
  - 유저가 직접 키보드로 입력해야하는 것을 명시
  - 메뉴판을 열고싶으면 `<kbd>Shift</kbd> + <kbd>F4</kbd>`
  - `<kbd>git init</kbd>`
- `<sub>`, `<sup>`
  - subscript, superscript
- `<i>`
  - 이탤릭 (italic)
  - `<i>` 요소는 목소리나 무드가 바뀌어야하는 텍스트, 관용구 분류 문안 기술 용어 같이 텍스트의 품질이
다른 것을 나타낼 때 사용한다. 예제: 웨스턴 텍스트의 배 이름
- `<b>`
  - 볼드 (bold)
  - b 요소는 특별히 중요하지는 않은데 실용적인 목적을 위해서 주목을 끌고싶을 때.. 사용하는 요소
- `<u>`
  - underline
  - u 요소는 텍스트에 레이블을 지정하고 싶거나 혹은 틀린 부분을 지적하고싶을 때 사용하라.
- `<mark>` (HTML 5.1에 추가)
  - 다른 텍스트에 비해 특정한 무언가를 마크하고 싶을 때 사용
  - 형광펜으로 밑줄 긋는 UI
  - highlight (약간 주목끌기 위한 목적)
- `<bdi>`
  - bdi 요소 내에 있는 콘텐츠를 다른 콘텐츠와 문맥상 격리
  - `<p>User <bdi>Jake</bdi> buyed Something</p>`
  - `<p>User <bdi> نسح/> bdi> buyer Something</p>`
  - **잘 안쓰임**
- `<bdo>`
  - 포맷을 분리
  - **잘 안쓰임**
- `<span>`
  - `<div>` 와 동일하나 특정한 텍스트에만 무언가 의미를 주고싶을 때 사용함
- `<br>`
  - 줄바꿈
  - `<br>` 요소를 CSS를 이용해서 display:none 을 주면 줄바꿈이 사라짐
- `<wbr>`
  - word break
  - 줄바꿈을 단어 단위로 바꾸어주는 요소
