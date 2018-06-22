### 작업 일정 산정하기
- 내가 생각한 일정 * 3
- 예외처리할 시간
  - 미디어 쿼리 분기를 태운다
  - 이미지 최적화를 한다
  - 해당 사이트의 기술스택을 어떻게 가져갈지 정한다
  - 접근성에 대한 대응
  - 디자인 Q&A
    - 컬러, 폰트사이즈 등 상의 (디자이너와)

### 컴포넌트 구조 파악하기
- 페이지 & 사이트에 어떤 컴포넌트들이 있고 그 컴포넌트를 어떻게 재조립할 수 있을지
  - 컴포넌트: 나눌 수 있는 최소한의 단위 UI
  - UI: 화면에 보이는 것 -> User Interface

### 먼저 하면 좋은 작업
1. 폰트(Typography)  -> 컨텐츠 작업을 먼저해야 박스 레이아웃이 잘짜진다 그렇지 않을경우 레이아웃이 깨질경우가 크다
1.사이즈
2.행간
3.자간
4.굵기
5.종류


#### PATH
- 모든 OS (Operating System)는 File System을 가지고 있다.
- PATH라는 것은 특정 파일의 경로를 지칭한다
> 04_FASTCAMPUS [폴더 / 디렉토리]
  / index.html
  / style.css

#### Fonts
- 웹 사이트 내의 타이포그래피를 정의
- font는 상속되기 때문에 HTML 요소나 BODY 요소에 먼저 선언
- font-size
  - 브라우저의 폰트 기본 사이즈 : 16px
- line-height
  - 행간 : line-height
     -  값으로 정수를 사용할 수 있음 : 1.2 (자기 자신의 폰트사이즈 * 값) 어떤 단위를 사용하여도 무관

- 폰트 패밀리 (font-family)
  - 기본 폰트 (Original fonts : OS에 기본적으로 깔려있는 폰트)
  - MAC OS X : APPLE SD Gothic NEO, 애플명조, 영문: San fransisco
  - Windows10 : 맑은 고딕, Malgeun Gothic, 돋움, 굴림, 궁서, 바탕 / 영문:
  - iOS : APPLE SD Gothic NEO, 애플명조 / 영문: San fransisco
  - 안드로이드 4.4이상 : Noto Sans CJK (본고딕) (구글에서 Noto sans를 권장) / Roboto
  - 안드로이드 4.3이하 : Droid Sans Fallback / Roboto (안드로이드 2.x) Droid sans
  - 삼성 : 삼성고딕
  - LG : LG스마트고딕
  - 팬텍 : 베가고딕
  - 도돌 런처 : 얘로 테마를 바꾸면 폰트가 바뀜. (강제) (4.3 이하)
  - 그 언어의 특정 형태의 폰트를 사용하는게 Generic Fonts
     - `sans-serif`: 삐침 없는 문자 (고딕)
     - `serif`: 삐침 없는 문자 (명조)
     - `monospace`: 고정폭 폰트 (개발용)
     - `fantasy`: 요상한 폰트(요상함)
     - `cursive`: 손글씨(손글씨)  
