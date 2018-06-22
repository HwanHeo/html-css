## Visual Formatting Model
> 유저 에이전트가 비주얼 미디어를 위해 문서 트리를 어떻게 해석하는가? visual formatting model에서
모든 요소는 0개 혹은 그 이상의 박스를 박스 모델에 따라 생성한다. 박스의 레이아웃은 다음과 같이 구성
되어있다.

- box dimension과 type
```
<p>사전지식 : box dimension (box model)</p>
    <!--
        BLOCK Level은 영역 전체를 차지함
        BLOCK Level은 box dimension의 영향을 받을 때,
        height가 콘텐츠의 높이 + padding top + padding-bottom

        box의 크기 계산법
        가로너비 : width + padding-left + padding-right + border-left + border-right
        세로높이 : height + padding-top + padding-bottom + border-top + border-bottom
        margin은 별도
    -->
    <div>치킨 맛있음.</div>

    <!--
        INLINE LEVEL은 콘텐츠 만큼만 영역을 가짐
        box의 크기 계산법
        너비 : content width + padding-left + padding-right + border-left + border-right
        높이 : line-height
    -->
    <span>치킨 맛있음.</span>

    <!--
        INLINE BLOCK

        box 자체는 inline처럼 배치
        box의 크기 계산법은 block을 따라감
        버튼 등을 만들 때 inline block을 활용
    -->
    <button>전송하기</button>
    <button>취소</button>
```

- 포지셔닝 스킴
  - normal flow 
    - 블록 레벨 엘리먼트는 블록으로 쌓이고, 인라인 레벨 엘리먼트는 인라인으로 쌓인다
    - CSS로 요소의 Flow를 바꾸지 않은 상태
  - floats
    - 요소를 배치하는 방법 중 하나. normal flow의 첫번째 위치로 레이아웃을 잡게하는 것.
    - float 속성을 넣게되는 경우 가능한 한 최대한의 left 혹은 right로 이동
    - floating -> 띄우는, 부양하는
    - float 속성은 특정한 요소를 왼쪽 or 오른쪽으로 부양시키는 역할
    - 속성값으로 left 혹은 right 를 가지게 됨
    - clearfix
       - float요소의 containing block이 제대로 높이를 가질 수 있게 하는 테크닉
```
.clearfix::after {
  content: '';
  display: block;
  clear: both;
  /* 형제 요소 중에 float요소가 있다면 그 float의 영향을 해제시켜주는 속성 */
  /* clear 속성을 넣어줌으로써 float영향을 받지 않게 된다*/
}
```
  - Absolute Positioning
    - Position 속성을 사용하게 될 경우, Containing block을 기준으로 박스를 특정 위치에 배치시키는 것이
가능. 이 상태를 absolute positioning 상태라 지칭한다.
    - Position : 특정한 요소를 어떻게 배치할 것인가
    - 특정한 위치에 해당 요소를 고정시키고 싶을 때
    - 해당 요소를 containing block을 기준으로 특정 위치에 고정시킬 수 있음 ( absolute )
    - box offset 속성 : top , right , bottom , left
    - Absolute Positing에서 containg block은 조상 요소 중 Position이 정적 Position이 아닌 요소
out-of-flow 상태
    - 콘텐츠 중첩 현상이 발생하기도 함
    - 다른 콘텐츠의 변화에 유동적으로 대응하기가 힘들다. (남발하지 마세요)
    - 위 케이스에서, floats나 absolute positioning을 이용해서 flow를 변경하는 상태 out-of-flow (flow에서 벗어났다) 라고 지칭함. 그 외의 경우는 in-flow(flow내에 있다 라고 지칭)  out-of-flow 상태에서는 예기치 못할 일이 많이 발생
  - containing block
    -  어떤 블럭들을 배치할 때 그 블럭들을 감싸고있는 블록
    -  어떤 블럭들을 배치할 때 그 블럭들의 루트요소(CSS)로써 활용되는 블록



```
<h1>박스 생성 제어하기</h1>
CSS 2.2에서 박스는 크게 두종류

<h2>Block level elements</h2>
<p> 포맷상 블럭으로써 취급되는것, 여기서 블럭이란 한 영역 전체를 차지하는 것</p>

<h2>Anonymous block level elements</h2>
<div>
  Example1 <!-- anonymous tag -->
  <p>Example2</p>
</div>

<h2>Inline level elements</h2>
<p>포맷상 텍스트로써 취급되는 것</p>
```