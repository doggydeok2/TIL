# HTML 문법 기초

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online.  
>
> https://heropy.blog/2019/04/24/html-css-starter/  



## 1. 기본 문법

- 태그는 각자의 의미를 가지고 있으며 다음과 같은 형태를 가짐
  - 열리고 닫히는 한 쌍의 구조를 가짐
  - 태그의 범위는 시작과 끝, 사이의 내용을 포함
    - 이를 포괄하여 하나의 요소(Element)라고 함

- 하단 `TAG` 부분에 유의미한 태그(Tag)의 이름이 들어감
  - Semantic Tag
- 태그가 닫히는 부분엔 `/`가 붙음

```html
<TAG></TAG>
<TAG>CONTENT</TAG>
```

```html
<h1>토끼와 거북이</h1>
<p>옛날 옛적에 토끼와 거북이가 살았습니다 ...</p>

<!-- 다음과 같이 이해할 수 있습니다. -->
<주제1>토끼와 거북이</주제1>
<문단>옛날 옛적에 토끼와 거북이가 살았습니다 ...</문단>
```

- 태그와 요소의 정확한 의미는 다르지만 혼용해서 쓰는 편



## 2. 속성(Attributes)과 값(Value)

- 태그의 이름만 가지고는 사용의 범위가 한정되어 있음
- 따라서, 해당 태그(요소)의 기능을 확장하기 위해 '속성'을 사용
  - 속성과 값은 한 세트로 작성
  - 속성들은 띄어쓰기로 구분
- 각 태그는 자신이 사용할 수 있는 속성과 값이 정해져 있음
  - 사용할 수 있는 속성과 없는 속성을 구분할 수 있어야 함
  - 잘 사용하지 않는 속성이 있으니 모든 속성과 값을 암기할 필요는 없음
- 필수 속성은 반드시 사용
  - `img`의 `alt` 속성 등 필수 속성은 반드시 작성해 웹 표준을 지킬 것

```html
<TAG 속성="값"></TAG>
```

```html
<img src="./my_photo.jpg" alt="내 프로필 사진" />
<div class="name">홍길동</div>

<!-- 다음과 같이 이해할 수 있습니다. -->
<이미지삽입 소스위치="./my_photo.jpg" 대체텍스트="내 프로필 사진" />
<의미없는분할 태그별명="name">홍길동</의미없는분할>
```



## 3. 부모 요소(Parent Element), 자식 요소(Child Element)

- 태그의 시작과 끝 사이에 들어갈 내용으로 또 다른 요소가 들어갈 수 있음
- 태그 A가 태그 B의 콘텐츠로 사용되면 태그 B는 태그 A의 부모 요소, 태그 A는 태그 B의 자식 요소라고 함
  - 자식의 자식 이하 요소들은 후손(자손, 하위) 요소라고 함
  - 부모의 부모 이상 요소들은 조상(상위) 요소라고 함
- 요소의 구조도는 이후 선택자를 통한 CSS 및 JS 적용에 중요하게 작용

```html
<PARENT>
  <CHILD></CHILD>
</PARENT>
```

```html
<section class="fruits">
  <h1>과일 목록</h1>
  <ul>
    <li>사과</li>
    <li>딸기</li>
    <li>바나나</li>
    <li>오렌지</li>
  </ul>  
</section>

<!-- 다음과 같이 이해할 수 있습니다. -->
<섹션영역 태그별명="fruits">
  <주제1>과일 목록</주제1>
  <순서없는목록>
    <항목>사과</항목>
    <항목>딸기</항목>
    <항목>바나나</항목>
    <항목>오렌지</항목>
  </순서없는목록>
</섹션영역>
```



## 4. 빈 태그(Empty Tag)

- 닫히는 개념이 없는(범위가 존재하지 않는) 태그
  - 태그가 위치한 그 부분에서 일을 해결
  - 태그의 의미를 확장하여 사용하는 속성과 값이 중요하게 작용
- HTML 버전에 따라 `/`가 태그의 끝에 붙거나 붙지 않음
  - HTML5에서는 두가지 모두 사용할 수 있음
  - 원하는 것을 사용하되 혼용하지 않는 것이 중요

```html
<!-- `/`가 없는 빈 태그 -->
<TAG>

<!-- `/`가 있는 빈 태그 -->
<TAG />
```



## 5. HTML 문서 구조

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



### 5-1. DOCTYPE(DTD, Document Type Definition)

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



### 5-2. HTML

- 해당 HTML 문서의 전체 범위를 설정
- 문서의 해석이 이루어질 시작과 끝을 알려줌

#### 5-2-1. lang

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



### 5-3. HEAD

- 해당 문서의 정보에 해당하는 부분
  - 화면을 구성하기 위한 기본 설정
- 문서에 출력되지 않음
  - `title`이 문서의 제목으로 표시되긴 하나 출력의 용도로 사용한 것은 아님

#### 5-3-1. TITLE

- HTML 문서(웹 페이지)의 제목을 정의
- 웹 브라우저의 각 사이트 탭에서 이름으로 표시됨
  - 접근성, 검색 엔진, 최적화 측면에서 도움이 되므로 적절한 제목을 입력

```html
<head>
    <title>NAVER</title>
</head>
```

#### 5-3-2. META

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
  - `content`는 `name`이나 `http-equiv` 속성의 값을 표현
  - 문서의 정보를 작성

```html
<head>
  <meta charset="UTF-8">
  <meta name="author" content="홍길동">
  <meta name="description" content="우리 사이트가 최고!">
</head>

<!-- 다음과 같이 이해할 수 있습니다. -->
<문서의정보범위>
  <정보 문자인코딩방식="UTF-8">
  <정보 정보종류="사이트제작자" 정보값="홍길동">
  <정보 정보종류="사이트설명" 정보값="우리 사이트가 최고!">
</문서의정보범위>
```

- `http-equiv`
  - 서버나 사용자의 환경에 작동 방식의 변경을 하는 지시사항을 작성
  - 각 브라우저별 최적화된 렌더링 방식 등을 지정
  - 이런 속성도 있다 정도

#### 5-3-3. LINK

- 외부 문서를 연결할 때 사용
  - 특히 HTML 외부에서 작성된 CSS나 아이콘 등을 불러와 연결할 때 사용
- 빈 태그
- `rel`
  - 필수 속성
  - 현재 문서와 연결할 외부 문서와의 관계를 지정
  - `stylesheet`, `icon` 등
- `href`
  - 외부 문서의 위치를 지정

```html
<head>
  <link rel="stylesheet" href="./css/main.css">
  <link rel="icon" href="./favicon.png">
</head>

<!-- 다음과 같이 이해할 수 있습니다. -->
<문서의정보범위>
  <외부문서연결 관계="CSS" 문서경로="./css/main.css">
  <외부문서연결 관계="사이트대표아이콘" 문서경로="./favicon.png">
</문서의정보범위>
```

#### 5-3-4. STYLE

- CSS를 HTML 문서 내부에서 작성할 때 사용

```html
<style>
  img {
    width: 100px;
    height: 200px;
  }
  p {
    font-size: 20px;
    font-weight: bold;
  }
</style>

<!-- 다음과 같이 이해할 수 있습니다. -->
<스타일정의>
  <!-- CSS 코드 -->
</스타일정의>
```

#### 5-3-5. SCRIPT

- HTML 문서 내부에 JS를 작성하거나, 외부의 JS를 불러와 연결할 때 사용

```html
<!-- 불러오기 -->
<script src="./js/main.js"></script>

<!-- 작성하기 -->
<script>
  function windowOnClickHandler(event) {
    console.log(event);
  }
  window.addEventListener('click', windowOnClickHandler);
</script>

<!-- 다음과 같이 이해할 수 있습니다. -->

<!-- 불러오기 -->
<자바스크립트 문서경로="./js/main.js"></자바스크립트>

<!-- 작성하기 -->
<자바스크립트>
  <!-- JS 코드 -->
</자바스크립트>
```



### 5-4. BODY

- 해당 문서의 구조에 해당하는 부분
  - 브라우저가 해석해야 할 HTML 문서의 구조 범위를 지정
  - 사용자가 화면을 통해 볼 수 있는 내용(콘텐츠)의 형태나 레이아웃 등을 의미
  - 로고, 헤더, 푸터, 네비게이션, 메뉴, 버튼, 입력창, 버튼, 팝업, 광고 등

#### 5-4-1. DIV

- 명확한 의미를 가지지 않는 분할(division)용 태그
- 단순히 특정 범위를 묶는(wrap) 용도로 사용
  - 주로 묶은 범위에 CSS나 JS를 적용

```html
<body>
  <div>
    <p></p>
  </div>
  <div>
    <div>
      <h1></h1>
      <p></p>
    </div>
  </div>
</body>

<!-- 다음과 같이 이해할 수 있습니다. -->
<body>
  <묶음1>
    <p></p>
  </묶음1>
  <묶음2>
    <묶음2-1>
      <h1></h1>
      <p></p>
    </묶음2-1>
  </묶음2>
</body>
```

#### 5-4-2. IMG

- HTML에 이미지를 삽입할 때 사용
- `src`
  - 필수 속성
  - 이미지의 URL
- `alt`
  - 필수 속성
  - 이미지의 대체 텍스트(alternate)를 지정

```html
<body>
  <img src="./kitty.png" alt="냥이">
</body>

<!-- 다음과 같이 이해할 수 있습니다. -->
<body>
  <이미지 경로="./kitty.png" 대체텍스트="냥이">
</body>
```



## 6. 웹 표준 검사

- [W3C validator](https://validator.w3.org/#validate_by_upload)에 파일을 업로드하여 HTML 문서가 표준에 부합하는지 테스트 가능

