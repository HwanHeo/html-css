## Animation
> A에서 B로가는 과정을 Frame화 시킨 것
   HTML Div 요소가  left: 150 -> left: 450
   150부터 450 사이를 n초동안 60fps로 이동하는 애니매이션

### transform **(변형)**
  - 비틀기 `skew()`
  - 회전 `rotate()`
  - 이동 `translate()`
    - position: relative로 같은 움직임을 구현 할수 있지만 position: relative 는 CPU에서 연산 후 GPU로 오기 때문에 끊킴이 심하다, translate는 GPU 에서만 동작하기 때문에 많은성능을 향상 시킬 수 있다
  - 크기조정 `scale()`

```
.skew {
    /* 항상 앞쪽 값이 X고 뒤 값이 Y */
    transform: skew(10px, 10px);
    transform: skewX(10deg);
    transform: skewY(10deg);
    letter-spacing: -0.5em;
     /* 흐릿하게해주는 속성 */
     filter: blur(4px); 
}

.rotate {
    /* 항상 앞쪽 값이 X고 뒤 값이 Y */
    transform: rotate(10deg, 10deg);
    transform: rotateX();
    transform: rotateY();
}

.translate {
    /* 항상 앞쪽 값이 X고 뒤 값이 Y */
    /* 자기 자신의 width와 height를 기준으로 이동하는 유일한 속성 */
    transform: translate(10deg, 10deg);
    transform: translateX();
    transform: translateY();
}

.scale {
    /* 
     *  정수로 표현된다 
     *  중앙에서 부터 크기가 조정된다
     */
    transform: scale(0);
    transform: scaleX();
    transform: scaleY();
}
```

### transition 
> A -> B로 바뀌는 과정을 자동으로 애니메이션화 시켜준다
   항상 trigger가 존재해야 한다. **(마우스를 올리는행위, 클릭 등등 이벤트 행위)**
- transition-duration
  -  이 애니메이션을 몇초동안 할 것인가?
- transition-property
  - 어떤 속성이 변경될 때 애니메이션을 걸건 지
- transition-timing-function **(중요)**
    - 애니메이션의 가속도
    - `linear`, `ease`, `ease-in`,  `ease-out`,  `ease-in-out`, `cubic-bezier`
- transition-delay
   - trigger 발동 후 몇 초 뒤에 애니메이션을 시작할 것인가?

```
/*
 *  transition: <transition-duration>, <transition-property>, <transition-timing-function>
 *  transition-delay: 0.6s;
 *  transition-delay  축약형으로 사용 불가하다
 */
.transition {
  /* 0.5초간 모든 애니메이션이 등속운동 */
  transition: 0.5s all linear;

  /* 0.5초간 margin-left만 양끝에서만 감속되게 */
  transition:0.5s margin-left ease;

  /* 0.5초간 margin-left만 끝에서만 감속되게 */
  transition:0.5s margin-left ease-out;

  /* 0.5초간 margin-left만 처음에만 감속되게 */
  transition:0.5s margin-left ease-in;

  /* 0.5초간 margin-left만 처음이랑 마지막에 감속 (약간 더 많이 감속) */
  transition:0.5s margin-left ease-in-out;

  /* 0.5초간 margin-left와 margin-top에만 애니메이션 */
  transition:0.5s margin-left ease-in-out, 0.5s margin-top ease-in-out;
}
```

### CSS Animation
>  특별한 트리거 없이 애니메이션을 실행한다.
    애니메이션 A - B - C - D - E - F 순으로도 할 수 있다.
    무한반복도 가능하다

- animation
  - animation-duration
    -  이 애니메이션을 몇초동안 할 것인가?
  - animation-delay
    - 몇 초 뒤에 애니메이션을 시작할 것인가?
  - animation-name
  - animation-timing-function
    - 애니메이션의 가속도
  - animation-play-sate
    - 재생: running 
    - 정지: paused
  - animation-fill-mode
    - 애니메이션이 끝났을대 되감기를 할건지, 그 상태를 유지 시킬건지
    - forwards: 끝나면 정지
    - backwards: 끝나면 처음으로 (default)
  - animation-iteration-count: 반복회수
    - 정수
    - infinite 무한대 
  - animation-direction: 끝나고 나서 애니메이션이 되돌아갈때 그 상태를 어떻게 처리할지
    - alternate
    - alternate-reverse
    - reverse

- keyframes
 
```
.loading {
  animation: 1s loading ease;
}

@keyframes loading {
   0% {
      width: 0;
   }
   100% {
      width: 100%;
   }
}

```
