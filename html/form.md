## Form
- 필수까지는 아니고 선택이다
- 웹에서 form이 동작하는 방식
  - 데이터를 수집
    - 데이터에는 필수(REQUIRED)인 것도 존재
    - 데이터에는 유효한 값과 유효하지 않은 값이 공존 (패턴) (되게 중요)
      - 이메일(e-mail) : xxx@xxx.com / xxx@xxx.cc
      - 전화번호(휴대폰) : 010-3761-9527 / 010-333-3333 / 010 333 3333 / (+82) 10 333 3333 / 02 3333 3333
      - 최댓값과 최솟값 (주문 / 수량제한 있을 때)
  - 데이터를 처리 => Form을 전송(submit)
    - 데이터를 처리할 때 바로 서버에 보내는 방법 (PHP, JAVA, Python 등으로 만들어진 웹서버의 특정 URL로 리다이렉션)
    - 데이터를 처리할 때 AJAX로 쏘는 방법 (백엔드 개발자가 API를 뚫어주면, 해당 API로 데이터를 말아서 보낸다)

### Input 
> 유저에게 데이터를 입력받기 위한 요소 
   대부분의 프로그래밍은 INPUT : OUTPUT 관계를 항상 유지한다
   HTML은 이 관계를 유지하지 않음

- mobile에서 `font-size`가 **16px** 일경우 zoom-in 이 되지 않는다
- input에 type 속성을 생략한 경우, type은 default text이다
- self closing input 
- type을 명시한 input 
  - `text`  HTML 4.01 때부터 존재하여 IE에서도 지원을 함 
  - `url` 모바일에서 키보드의 형태가 달라짐
  - `tel` 전화번호를 입력받기 위한, 숫자키패드만 노출된다
  - `email` 이메일을 입력받기 위한 input
  - `search` 키패드 아래버튼이 **검색**으로 바뀌고, 키패드위에 입력했던 예제들이 나타난다
  - `number` 숫자와 기호들이 나타난다
  - `date` 날짜를 선택하는 키패드 노출
  - `radio` 여러개의 값중 단일 선택이 필요시 사용된다
  - `checkbox` 여러개의 값중 다중 선택이 필요시 사용된다
  - `password` 유저가 노출되고 싶지않은 값들 사용시
>  input 요소들은 거의 대부분 모바일에서만 사용된다.
    데스크탑에선 input type="text"  버전별로 다르고 지원율로 달라서
    **커스터마이징 불가능 **
```
1. 이 input은 type 속성을 생략하고 있다
<input>

2.  1과 차이는 없음 / 그냥 컨벤션 차이
<input />

3. type을 생략한 경우 암묵적으로 text이기 때문에 1과 2와 차이점은 없다
    CSS에선 차이가 날 수도 있다 type명시하는것을 권장
<input type="text">
 
3-1. text
<input type="text">

3-2. url
<input type="url">

3-3. tel
<input type="tel">

3-4. email
<input type="email">

3-5. search
<input type="search">

3-6. number
<input type="number">
    
3-8. date / 날짜
<input type="date">

3-9 radio 
<label><input type="radio" name="gender"> 남자</label>
<label><input type="radio" name="gender"> 여자</label>

3-10. checkbox
<label><input type="checkbox" name="favorite"> XBOX 360</label>
<label><input type="checkbox" name="favorite"> MS OFFICE</label>
<label><input type="checkbox" name="favorite"> Windows</label>

3-11. password
<input type="password">
```

### Input Attribute
- type
  - text
- required
  - 입력값이 필수일 경우
- placeholder
  - 입력값이 어떤 데이터가 들어가는지 유저에게 알려주는 힌트
  - label과 placeholder를 혼용하면 안된다
    -  UX 상에서 좋지않은 구현
- name
  - from을 처리할때 처리하는 속성
  - name속성의 값을 전세계에서 많이 쓰는 키워드로 쓰면 자동완성이 활성화 된다
    - `email`, `address`, `postal`, `zip`, `region`, `phone`, `mobile`, `ccname`, `ccnumber`, `cvc`, `ccmonth`, `ccyear`, `username`, `password`
- autofocus
  - 이 요소에 먼저 포커스가 가야 할때
  - 유저의 flow를 빼앗는 행위여서 신중히 써야하는 기능중 하나 (주의해야한다)
- min, max (값 제한)
  - `type=number` 최소값과 최대값을 정의 할 수 있다
- minlength, maxlength 
  - 입력값에 최소길이와 최대길이를 제한한다