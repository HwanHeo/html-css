## Colors and Backgrounds
> HTML요소에 색상과 이미지를 넣는다

### color
- 특정한 요소의 Content의 전경색을 지정한다.
  - 특정요소란 Selector를 지칭한다
- 해당 웹사이트에서 자주쓰이는 common 컨텐츠들은 미리 작성을 해준다.
  - primary color, secondary color, background color 등등..
#### Hex value
- 16진수 6개로 이루어진 색상 표현법
- 0에 가까울 수록 어둡고, F에 가까울 수록 밝은 색.
- 기존의 디자인 도구 : PhotoShop (예로부터 이 친구는 Hex 값 복붙이 제일 쉬움)
- 편해서 많이 사용
- 컬러 자체에 Alpha값을 포함할 수 없음.

```css
body {
 color: #FFFFFF; /* 비권장 */
 color: #ffffff; /* 권장 */
}
```

#### rgba(0, 0, 0, 1)
- Red, Green, Blue, Alpha
- RGB = 0부터 255부터까지의 값(16진수의 최대값 = 255)
- Alpha
  - 10% = 0.1
  - 1% = 0.01
  - 0.1% = 0.001
- 협업할 때 디자이너에게 Alpha값 사용은 되도록이면 배경이 비춰야할 때만 사용해달라고 요청

#### HSLA
- 표준에서는  이 값이 사용하기 편하다고 되어있으나 잘 사용되지 않는다.
- H = Hue
- S = Saturation 
- L = Lightness
- A = Alpha

```css
.color {
  color: hsla(330, 100%, 50%, 1)
}
```

#### opacity
- 해당요소 전체를 투명하게 만든다
```css
body {
  opacity: 0; /* 투명 */
  opacity: 1; 
}
```

#### background
```html
<div class="box"></div>
<div class="box box-red"></div>
<div class="box box-blue"></div>
<div class="box box-images"></div>
<div class="box box-gradient-linear"></div>
<div class="box box-gradient-radiel"></div>
```

```css
.box {
  float: left;
  width: 150px;
  height: 150px;
  border: 1px solid #666666;
  margin: 15px 7.5px;
}
/*
 * 기본적으로 box(대부분 요소)의 배경색은 trasnparent(투명)
 */
.box {
  /* color */
  background: royalblue;
  background-color: royalblue;
}

.box-red {
  background: crimson;
}

.box-images {
  background: url("경로");
  /*
   * 배경을 이미지로 가져오면 배경 이미지는 그대로인데...
   * 박스 사이즈는 부족해서 이미지가 다 보이지 않을 수 있음
   */
  background-size: cover;
  /*
   * background-size를 cover로 넣어주면,
   * 배경 이미지가 해당 박스에 맞게 줄어들어서 들어감
   */
  background-position:0 0;
  /*
   * background-position: <pos-x> <pos-y>
   * left top
   * right top
   * left bottom
   * right bottom
   * center top
   * center center
   */
  background-repeat: no-repeat;
  /*
   * repeat : 반복
   * repeat-x : x축으로만 반복
   * repeat-y : y축으로만 반복
   * repeat : 반복
   * no-repeat : 반복안함
   */

background: url("경로") 0 0 no-repeat #000;
  /*
   * background:
   * background-image
   * background-position
   * background-repeat
   * background-color
   */
}

/*
 * 웹에서 gradient는 이미지로써 취급
 * 배경 이미지는 여러개 작성이 가능 (multiple background)
 */
.box-gradient-linear {
  background: linear-gradient(90deg, royalblue, blue),
    linear-gradient(37deg, red, blue),
    linear-gradient(135deg, green, blue);
}

/*
 * 방사형 gradient
 */
.box-gradient-radial {
  background: radial-gradient(circle at center, hotpink, red)
}

```


#### Shadow
```html
<div class="box"></div>
<div class="box box-shadow"></div>
<div class="box box-inner-shadow"></div>
<div class="box box-multi-shadow"></div>

<strong>This is good</strong>
```

```css
.box {
  float:left;
  width:150px;
  height:150px;
  border:1px solid #666666;
  margin:15px 7.5px;
}

/*
 * shadow = 그림자
 * x 이동
 * y 이동
 * spread - 펼치다
 * shadow color
 */
.box-shadow {
  box-shadow: 5px 5px 5px rgba(0,0,0,0.5);
}

/*
 * inset shadow
 */
.box-inner-shadow {
  box-shadow: inset 5px 5px 20px rgba(0,0,0,0.2);
}
/*
 * multi
 */
.box-multi-shadow {
  box-shadow: 5px 5px 20px rgba(0,0,0,0.2),
    -5px -5px 20px olive;
}

/*
 * text-shadow
 * Mobile 기기 중 하위단말에서는
 * shadow를 넣을경우 극심한 성능저하
 */
strong {
  clear: both;
  text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
}
```
