# HTML 요소-주요 범위 & 메타데이터

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. 블록(Block), 인라인(Inline)

- HTML엔 크게 블록 요소와 인라인 요소가 존재
- 현재 완전히 적용되는 내용은 아니지만, HTML과 CSS를 같이 사용함에 있어 숙지해야 할 내용



### 1-1. 블록 요소

- div, h1, p 등
- 레이아웃을 잡는 용도로 사용
- 사용 가능한 최대 가로 너비를 사용
  - 초기값: `width: auto;` `height: auto;`
- 크기를 지정할 수 있음
  - 별도의 설정이 없다면, `width: 100%;` `height: 0;`
  - 단 `height`는 내용의 길이만큼 늘어나며, `height: 0;`등의 설정이 있다면 우선 반영됨

```css
div {
  background: red;
  width: 200px;
  height: 20px;
}
```

- 수직으로 쌓임
- 상하좌우 `margin` 및 `padding` 사용 가능

```css
div {
  ...
  margin: 20px;
  padding: 20px;
}
```

```html
<body>
  <div>안녕하세요!</div>
  <div>안녕하세요!</div>
  <div>안녕하세요!</div>
  <div>안녕하세요!</div>
  <div>안녕하세요!</div>
</body>
```



### 1-2. 인라인 요소

- span, img 등
- TEXT를 다루는 용도로 사용
- 필요한 만큼의 가로 너비를 사용
  - 초기값: `width: 0;` `height: 0;`
- 크기를 지정할 수 없음

```css
span {
  background: yellow;
  width: 200px;  /* 적용되지 않음 */
  height: 150px;  /* 적용되지 않음 */
}
```

- 수평으로 쌓임
  - 각 `<span>` 사이에는 띄어쓰기가 적용
  - 띄어쓰기를 원하지 않을 때, `<span>`을 붙여 사용하거나(한 줄에 여럿 작성하거나) 별도의 후처리 필요
    - 후처리는 margin 등을 사용

- 좌우 `margin` 및 `padding` 사용 가능
  - 상하 ` margin`과 `padding`은 사용할 수 없음
  - `padding`이 시각적인 확인은 가능하나, 실질적인 거리를 만들어내지 못하므로 원하는 사용이 불가

```css
span {
  ...
  margin: 20px;  /* 좌우만 적용 */
  padding: 20px;  /* 상하좌우가 다 커지나, 상하 padding이 실질 거리를 만들어내지 못함 */
}
```

```html
<body>
  <span>안녕하세요!</span><span>안녕하세요!</span><span>안녕하세요!</span>
  <span>안녕하세요!</span>
  <span>안녕하세요!</span>
  <div>동해물과 백두산이 마르고 닳도록</div>  <!-- span의 padding 영역을 침범하게 됨  -->
</body>
```



### 1-3. DISPLAY

- 블록, 인라인 등 요소의 성질을 구분하는 CSS 속성
- 블록 요소의 기본값은 `display: block;`이며, 인라인 요소의 기본값은 `display: inline;`
- 위 속성을 선택자에 기입하여, 각 요소의 display 값을 임의로 전환할 수 있음



## 2. 메타데이터

> 02 HTML 문법 기초 05. HTML 문서 구조 Cont.
>
> https://developer.mozilla.org/ko/docs/Web/HTML/Element

- 전체 문서의 범위를 설정하기 위해 `<html>`, `<head>`, `<body>` 등의 태그를 사용
  - 문서 내에서 같은 태그를 반복해서 사용할 수 없음

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="author" content="홍길동">
    <meta name="description" content="우리 사이트가 최고!">
    <title>내 사이트</title>
    <link rel="stylesheet" href="./css/main.css">
    <script src="./js/main.js"></script>
</head>
<body>
    <section>
      <h1></h1>
      <div>
        <ul>
          <li></li>
          <li></li>
        </ul>
      </div>
    </section>
</body>
</html>
```



### 2-1. DOCTYPE(DTD, Document Type Definition)

- 마크업 언어에서 문서 형식을 정의
  - 태그가 아님
  - 문서가 브라우저에서 어떤 HTML 버전으로 해석되어 구조화 및 출력될 것인가?
  - HTML은 크게 1, 2, 3, 4, X-, 5 버전이 존재하며 현재의 표준은 HTML5

```html
<!-- HTML 5 -->
<!DOCTYPE html>

<!-- XHTML 1.0 Transitional -->
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```



### 2-2. HTML

- 해당 HTML 문서의 전체 범위를 설정
- 문서의 해석이 이루어질 시작과 끝을 알려줌

#### 2-2-1. lang

- 문서가 어느 언어로 작성되었는지 표시
- 검색 엔진이나 브라우저가 참고할 수 있도록 작성
- `en`, `ko` 등 [ISO 639-1 코드 목록](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D)에 있는 언어 종류를 값으로 사용

```html
<!DOCTYPE html>
<html>
  <head>
    문서의 정보
  </head>
  <body>
    문서의 구조
  </body>
</html>
```



### 2-3. HEAD

- 해당 문서의 정보에 해당하는 부분
  - 화면을 구성하기 위한 기본 설정
- 문서에 출력되지 않음
  - `title`이 문서의 제목으로 표시되긴 하나 출력의 용도로 사용한 것은 아님

#### 2-3-1. TITLE

- HTML 문서(웹 페이지)의 제목을 정의
- 웹 브라우저의 각 사이트 탭에서 이름으로 표시됨
  - 접근성, 검색 엔진, 최적화 측면에서 도움이 되므로 적절한 제목을 입력

```html
<head>
    <title>NAVER</title>
</head>
```

#### 2-3-2. META

- HTML 문서에 관한 정보(표시 방식, 제작자(소유자), 내용, 키워드 등 메타데이터)을 검색엔진이나 브라우저에 제공
  - HEAD 태그 내 자식 태그들로 나타낼 수 없는 정보들을 나타낼 때 사용
- 빈 태그

- `charset`
  - 문자 인코딩 방식을 설정
  - 텍스트를 화면에 렌더링하는 방식을 설정
  - `UTF-8`, `EUC-KR` 등
    - `UTF-8`의 경우 CJK(China-Japan-Korea) 언어의 표현에 특화된 조합형 인코딩 방식
    - `EUC-KR`은 조립된 글자를 찾아오므로 글자가 깨질 수 있는 완성형 인코딩 방식
  - 반드시 넣어줄 필요가 있음
- `name`, `content`
  - `name`은 문서 레벨의 메타데이터 이름을 정의
    - `author`, `description`, `keywords`, `viewport` 등
    - `viewport`: 반응형 웹사이트를 제공하기 위해, 정보를 렌더링할 화면의 영역을 설정
  - `content`는 `name`이나 `http-equiv` 속성의 값을 표현
  - 문서의 정보를 작성

```html
<head>
  <meta charset="UTF-8">
  <meta name="author" content="홍길동">
  <meta name="description" content="우리 사이트가 최고!">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="IE-edge">
</head>
```

- `http-equiv`
  - 서버나 사용자의 환경에 작동 방식의 변경을 하는 지시사항을 작성
  - 각 브라우저별 최적화된 렌더링 방식 등을 지정
  - 예: `<meta http-equiv="X-UA-Compatible" content="IE-edge">`
    - Internet Explorer에서 렌더링될 때, 최신의 렌더링 방식으로 출력하도록 적용

#### 2-3-3. LINK

- 외부 문서를 연결할 때 사용
  - 특히 HTML 외부에서 작성된 CSS나 아이콘 등을 불러와 연결할 때 사용
- 빈 태그
- `rel`
  - 필수 속성
  - 현재 문서와 연결할 외부 문서와의 관계를 지정
  - `stylesheet`, `icon` 등 다수 존재
- `href`
  - 외부 문서의 위치를 지정
  - 절대 경로와 상대 경로가 존재
  - `hreflang`
    - 링크된 리소승의 언어를 나타냄
    - `href`가 존재할 때만 사용해야 하며, 참고용이므로 작성하지 않아도 무방
- 이외 `crossorigin`, `disabled`, `media`  등

```html
<head>
  <link rel="stylesheet" href="./css/main.css">
  <link rel="icon" href="./favicon.png">
</head>
```

#### 2-3-4. STYLE

- CSS를 HTML 문서 내부에서 작성할 때 사용
- `<body>` 태그 안에도 작성할 수 있으나, 동작 프로세스에서 `<head>`에 작성한 만큼 효율적이진 않음
- `type`
  - 스타일 태그 안에 어떠한 유형의 내용을 넣을 것인지 명시
  - 기본값은 `type="text/css"`로, text/css 사용 시 명시하지 않아도 무방
- 이외 `media`, `title` 등이 있으나, 대안이 있어 잘 사용하지 않음

```html
<style type="text/css">
  img {
    width: 100px;
    height: 200px;
  }
  p {
    font-size: 20px;
    font-weight: bold;
  }
</style>
```

#### 2-3-5. MIME Type

- 전송되는 문서의 유형을, `type`을 통해 명시하는 매커니즘
- `text/html`, `image/jpeg`, `audio/*`, `video/mp4` 등의 타입이 존재
  - 외우면 좋으나, 필요에 따라 찾아쓰는 것을 보다 권장

#### 2-3-6. BASE

- 문서 안의 상대 URL이 사용할 기준 URL을 지정
  - 기준을 잡는 것이므로, 문서 내에서 단 한 번만 사용 가능

- 작성된 경로는 문서 내 모든 상대 경로에 영향을 끼침

```html
<link rel="stylesheet" href="./css/main.css">

<!-- 위와 아래 태그는 동일하게 동작 -->

<base href="./css/">
<link rel="stylesheet" href="main.css">
```

