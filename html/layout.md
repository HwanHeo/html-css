## Layout

### Block formatting context
- demention
  - 요소를 어디에 얼만큰 보여줄지
- 가질 수 있는 X축 영역을 다 가진다(width과 관계없이)
  - 완충제
    - padding
    - margin
### Inline formatting context
- inline 요소에 float속성을 적용할경우 display: block으로 변한다(float box)
- float의 clear는 block박스에서만 적용이 된다

### Line Box
- 기본으로  block값을 가진다
- block 요소의 영향을 받는다
  - inline 혹은 text인경우

### flex box
- 레이아웃을 위한 css
- float는 레이아웃을 위한 css가 아니다
- flexbox는 CSS3 (IE 10 부터 지원, IE11 이하, 안드로이드 4.4 미만에서 버그가 많다) 
- display: flex
  - flexible box라는 영역을 생성한다
  - flexible box 내의 자식 요소들은 마음껏 늘이거나 줄이거나 순서를 바꾸거나 할 수 있다.
  - flexible box는 기본적으로 줄바꿈이 일어나지 않는다.(속성을 이용했을경우는 가능)
  - 만약 flexible box 영역이 자식요소의 box영역을 다 합한것보다 작다면 자식요소를 알아서 줄어든다.
  - flexible box 내부는 제어권이 무한
- main-axis, cross-axis
  - flexible box 내의 요소가 쌓이는 방향
  - main-axis 방향으로 쌓임
  - main-axis의 교차 축으로 쌓이는게 cross-axis
  - main-axis 변경: flex-direction
  - main-axis를 변경하면  cross-axis같이변경됨

#### flex
- flex-direction
  - row : 좌 - 우
  - row-reverse : 우 - 좌
  - column : 상 - 하
  - column-reverse : 하 - 상
- justify-content
  - flex-start : main-axis의 start point
  - center : 중앙
  - flex-end : main-axis의 end point
  - space-between : 양끝 정렬
  - space-around : 동일한 간격
- align-items 
  - flex-start : cross-axis의 start point
  - center : 중앙
  - flex-end : closs-axis의 end point
  - stretch : 늘여뜨리기 (기본값)
- flex-wrap
  - nowrap : 줄바꿈 안함
  - wrap : 줄바꿈 함
- align-content 
  - align-items : cross-axis 
  - flex-start : cross-axis의 start point
  - center : 중앙
  - flex-end : closs-axis의 end point
  - stretch : 늘여뜨리기 (기본값)
  - space-around : 같은 간격
  - space-between : 양끝정렬
```css
/* as-is */
.container::after {
      content:'';
      display:block;
      clear:both;
}
.container .box {
      float:left;
     width:33.333333%;
}

/* to-be */
.container-flex {
      display:flex;
     /*
      * flex-direction
      * row : 좌 - 우
      * row-reverse : 우 - 좌
      * column : 상 - 하
      * column-reverse : 하 - 상
      */
     /*
      * justify-content: main-axis 정렬
      * flex-start : main-axis의 start point
      * center : 중앙
      * flex-end : main-axis의 end point
      * space-between : 양끝 정렬
      * space-around : 동일한 간격
      */
      justify-content: space-between;
    /*
     * flex가 한줄일 경우에 동작
     * align-items : cross-axis 
     * flex-start : cross-axis의 start point
     * center : 중앙 (!)
     * flex-end : closs-axis의 end point
     * stretch : 늘여뜨리기 (기본값)
     */
     align-items:center;
     /*
      * 자식요소가 부모요소의 영역을 넘어섰을 때
      * 어떻게 처리할 지
      * flex-wrap
      * nowrap : 줄바꿈 안함
      * wrap : 줄바꿈 함
      */
     flex-wrap:wrap;
    /*
     * align-content : cross axis 기준 box 전체가 같이 정렬
     * align-items : cross-axis 
     * flex-start : cross-axis의 start point
     * center : 중앙 (!)
     * flex-end : closs-axis의 end point
     * stretch : 늘여뜨리기 (기본값)
     * space-around : 같은 간격
     * space-between : 양끝정렬
     */
    align-content: stretch;
    height: 500px;
}
.box {
    padding:10px;
    margin:10px;
    background:royalblue;
    color:white;
}

```
