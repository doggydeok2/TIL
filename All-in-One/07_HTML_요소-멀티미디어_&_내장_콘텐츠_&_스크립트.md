# HTML 요소-멀티미디어 & 내장 콘텐츠 & 스크립트

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. 멀티미디어

### 1-1. IMG

> https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/

- 이미지를 삽입
- 빈 태그
- `src`
  - 필수 속성
  - 이미지의 URL을 의미
- `alt`
  - 필수 속성
  - 이미지의 대체 텍스트
- `width`, `height`
  - 이미지의 가로/세로 너비
  - 둘 중 하나만 설정할 시, 이미지의 비율을 유지하게끔 다른 하나도 자동으로 변경됨
    - 크기의 조절을 위해서라면 하나만 입력하는 것을 권장
  - 속성을 사용하는 대신, CSS를 통해서도 조절이 가능

- `srcset`, `sizes`
  - `srcset`: 브라우저에게 제시할 이미지 URL과 원본 크기의 목록을 정의
    - 브라우저가 자동으로 화면 크기(뷰포트 너비)에 걸맞은 적절한 이미지를 사용
  - `sizes`: 미디어 조건과, 해당 조건일 때 이미지 최적화 크기의 목록을 정의
  - 반응형 웹사이트에 사용
  - `srcset` 속성값은 `파일명 크기w,`의 목록으로 구성
    - 사용할 이미지를, 사이즈별로 2장 이상 준비하여 작성
    - 한 장만 사용할 경우, `srcset` 대신 `src`를 사용하면 됨
    - 이미지 크기는 `px` 단위가 아닌 `w` 혹은 `x`를 사용해야 하며, 작은 크기부터 순서대로 입력
    - `width`를 통해 고정된 이미지 크기를 유지할 수도 있음
  - `sizes` 속성값은 `(미디어 조건) 최적화 이미지 크기`의 목록으로 구성
    - `sizes="(min-width: 1000px) 700px"`라면, 뷰포트 너비가 1000px 이상일 때 이미지를 700px로 최적화 출력하겠다는 의미
    - `width`는 이미지의 출력 크기만 지정하는 반면, `sizes`는 출력 크기와 최적 크기를 함께 지정
      - `sizes`를 사용 시 해당 출력 크기에 가장 적합한 이미지를 `srcset`에서 골라 사용
      - 두 속성을 동시에 사용할 경우 `width`가 우선 적용
  - `w`, `x`
    - `w`는 이미지의 원본 크기(가로 너비)를, `x`는 이미지의 비율을 의미



### 1-2. AUDIO

- 소리 콘텐츠(MP3)를 삽입
- `autoplay`
  - 소리 콘텐츠가 준비되는 순간, 바로 재생
- `controls`
  - 재생, 정지 등 제어 메뉴를 표시
  - 없을 시, CSS가 지정되어 있지 않다면 아무 것도 출력되지 않음
- `loop`
  - 재생이 끝났을 시 처음부터 반복하여 재생
- `preload`
  - 페이지가 로드될 때, 파일을 로드할지 지정
  - `autoplay`가 지정되어 있다면 해당 속성은 무시됨
  - 속성값 `none`은 플레이 버튼을 누르기 전까지 로드하지 않음
  - 속성값 `metadata`는 메타데이터만 미리 로드. 기본값
  - 속성값 `auto`는 사용자가 플레이 버튼을 누르기 전에도 전체 파일을 로드
- `src`
  - 콘텐츠의 URL
- `muted`
  - 음소거 여부
- 자세한 부분의 제어(음량 크기, 구간 반복, 시작 지점 등)은 JavaScript를 통해 진행하게 됨



### 1-3. VIDEO

- 동영상 콘텐츠(MP4)를 삽입
- `autoplay`
  - 동영상 콘텐츠가 준비되는 순간, 바로 재생
- `controls`
  - 재생, 정지 등 제어 메뉴를 표시
- `crossorigin`
  - 콘텐츠를 가져올 때, CORS를 사용해야 하는지 여부
  - `anonymous`, `use-credentials` 등
- `loop`
  - 재생이 끝났을 시 처음부터 반복하여 재생
- `muted`
  - 음소거 여부
- `poster`
  - 동영상 썸네일 이미지 URL
- `preload`
  - 페이지가 로드될 때, 파일을 로드할지 지정
  - `autoplay`가 지정되어 있다면 해당 속성은 무시됨
  - 속성값 `none`은 플레이 버튼을 누르기 전까지 로드하지 않음
  - 속성값 `metadata`는 메타데이터만 미리 로드. 기본값
  - 속성값 `auto`는 사용자가 플레이 버튼을 누르기 전에도 전체 파일을 로드

- `src`
  - 콘텐츠의 URL
- `width`, `height`
  - 동영상의 가로/세로 너비



### 1-4. FIGURE, FIGCAPTION

- `<figure>`는 이미지나 삽화, 도표 등의 영역을 설정
- `<figcaption>`은 `<figure>`에 포함되어, 이미지나 삽화 등의 설명을 표시
  - 브라우저나 검색엔진 등이 정보를 확인할 때 유용

```html
<figure>
  <img src="images/cat.jpg" alt="CAT">
  <figcaption>고양이 이미지입니다!</figcaption>
</figure>
```



## 2. 내장 콘텐츠

### 2-1. IFRAME

- 다른 HTML 페이지를 현재 페이지에 삽입
  - 중첩된 브라우저 컨텍스트(프레임)를 표시
- `name`
  - 프레임의 이름을 의미
  - 페이지에 여러 `<iframe>`이 들어갈 경우, 고유한 이름을 명명해주면 좋음
- `src`
  - 포함할 문서의 URL
- `width`, `height`
  - 프레임의 가로/세로 너비
- `allowfullscreen`
  - 전체 화면 모드 사용 여부
- `frameborder`
  - 프레임 테두리 사용 여부
  - 기본값은 1(테두리 있음)이나, 0(테두리 없음) 설정 후 별도의 CSS로 테두리를 만들어주는 편
- `sandbox`
  - 보안을 위한 읽기 전용으로 삽입
    - `<iframe>` 내에서 HTML을 불러올 경우, 각종 보안 이슈가 발생할 수 있기 때문
  - 사용 시, 불러온 HTML 내의 기능이 일부 동작하지 않을 수 있음
  - `allow-form`(양식 제출 가능), `allow-scripts`(스크립트(JavaScript 등) 실행 가능), `allow-same-origin`(같은 출처(도메인)의 리소스 사용 가능) 등의 속성으로, 보안을 챙기며 기능을 사용하는 편



### 2-2. CANVAS

- Canvas API나 WebGL API를 사용하여, 그래픽이나 애니메이션을 랜더링
  - `<canvas>`는 그래픽을 랜더링할 영역을 설정
  - JavaScript를 알아야 제대로 된 제어를 할 수 있음
- `width`, `height`
  - 캔버스의 가로/세로 너비

```html
<canvas id="canvas" width="200" height="150"0></canvas>
<script>
  const canvas = document.getElementById('canvas');
  const ctx = canvas.getContext('2d');
  ctx.fillStyle = 'rgb(200, 0, 0)';
  ctx.fillRect(10, 10, 50, 50);
  ctx.fillStyle = 'rgba(0, 0, 200, 0.5)';
  ctx.fillRect(30, 30, 50, 50);
</script>
```



## 3. 스크립트

### 3-1. SCRIPT

- 스크립트 코드를 문서에 포함하거나 참조(외부 스크립트)
- `async`
  - 스크립트의 비동기적(Asynchronously) 실행 여부
  - `src` 속성이 필수
- `defer`
  - 문서 파싱(구문 분석)후 작동 여부
    - JavaScript가 HTML 코드를 분석해 실행하는 경우가 존재
    - 실행하는 JavaScript 코드가 언제 동작하느냐에 따라, 동작 성공 여부가 결정되는 경우가 있음
      - 코드는 위에서 아래로 읽히기 때문
      - `<script>`가 `<body>`의 최하단에 오는 이유이기도 함
    - 속성 설정 시, HTML 코드를 모두 분석한 후 해당 `<script>` `src` 내 코드가 동작
      - `<body>`의 최하단에 `<script>`를 작성하지 않아도 됨
      - 두 방법 모두 자주 사용
  - `src` 속성 필수

- `src`
  - 참조할 외부 스크립트 URL
  - 속성이 명시된 해당 `<script>` 코드 내에, 포함된 스크립트 코드는 무시됨

- `type`
  - MIME 타입
  - 기본값은 `text/javascript`



### 3-2. NOSCRIPT

- 스크립트를 지원하지 않는 경우, 삽입할 HTML을 정의
  - `<script>` 코드가 동작하지 못할 경우 출력되는 대체 HTML

