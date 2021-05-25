# CSS 기초

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online.  
>
> https://heropy.blog/2019/04/24/html-css-starter/  



## 1. 기본 CSS 구조

- 선택자, 속성, 값으로 구성
  - 선택자에 적용할 스타일(CSS)을 중괄호 안에 기입
  - 각 `속성: 값`들은 세미콜론(`;`)으로 구분
- 유지보수의 용이를 위해, 각 CSS는 HTML 문서에 적용되는 순서대로 작성하는 것이 좋음

```css
div {
  font-size: 20px;
  color: red;
}

/* 다음과 같이 이해할 수 있습니다. */
선택자 {
  속성: 값;
  속성: 값;
}
```



### 1-1. 선택자(Selector)

- HTML에 스타일을 적용하기 위해 HTML의 특정 요소를 선택하는 사인(sign)
- 속성과 값들을 적용할 요소를 특정할 수 있게끔 기입

```html
<div>
  <h1>제목</h1>
  <p>본문</p>
</div>
```

```css
h1 {
  color: red;
}
p {
  color: blue;
}
```



### 1-2. 속성(Properties)과 값(Value)

- 적용할 스타일을 정의
- 많이 아는 것이 중요
  - 보다 다양한, 원하는 스타일을 만들기 위해선 무엇이 필요한지 알아야 함

```css
div {
  color: red; /* 글자색은 빨강 */
  font-size: 20px; /* 글자 크기는 20px */
  width: 300px; /* 가로 너비는 300px */
  margin: 20px; /* 바깥 여백은 20px */
  padding: 10px 20px; /* 안쪽 여백은 위아래 10px, 좌우 20px */
  position: absolute; /* 위치는 부모 요소 기준... */
}
```



## 2. 선언 방식

### 2-1. 태그에 직접 작성(Inline)

- 태그 속성 `style`에 값으로 CSS `속성: 값;`을 작성
- 태그에 직접 넣으므로 선택자가 필요하지 않음
- 작성 및 수정의 관점에서 권장하지 않는 방식
  - 속성 적용을 원하는 모든 태그에 일일히 작성해야 함
  - 나쁜 방식인 것은 아님
    - JS에서 CSS에 접근하는 등의 상황에서 사용할 여지가 있음

```html
<div style="color: red;">태그에 직접 작성1</div> <!-- red -->
<div style="color: red;">태그에 직접 작성2</div> <!-- red -->
<div style="color: red;">태그에 직접 작성3</div> <!-- red -->
<div style="color: red;">태그에 직접 작성4</div> <!-- red -->
```



### 2-2. HTML에 내장(Embeded)

- HTML 문서의 `<head>`의 `<style></style>` 태그 내용으로 CSS를 작성
- CSS만 별개로 작성하므로 선택자가 필요

```html
<head>
  <style>
    div {
      color: red;
    }
  </style>  
</head>
<body>
  <div>HTML에 포함1</div> <!-- red -->
  <div>HTML에 포함2</div> <!-- red -->
  <div>HTML에 포함3</div> <!-- red -->
</body>
```



### 2-3. HTML 외부에서 불러오기(Link)

- CSS를 완전히 분리된 문서에서 작성
- 분리된 파일을 여러 HTML 파일이 불러와 사용할 수 있음
  - 복수의 파일에 일괄 적용할 수 있는 것이 큰 장점
  - `<link>` 태그에 `rel="stylesheet"`, `href="경로"`를 속성으로 기입

```html
<!-- HTML 1 -->
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기1</div> <!-- red -->
</body>
```

```html
<!-- HTML 2 -->
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기2</div> <!-- red -->
</body>
```

```css
/* main.css */
div {
  color: red;
}
```



## 3. 선택자(Selector) Cont.

- 선택자는 HTML 특정한 요소를 선택하기 위해 사용
- 원하는 선택자만을 정확히 특정하기 위해서 여러 종류의 선택자가 존재
  - 대표적으로 사용되는 것은 두 가지
- 선택자를 여럿 나열하여 사용할 수도 있음
  - 이 경우 오른쪽의 선택자가 왼쪽 선택자의 하위 요소가 됨



### 3-1. 태그(Tag)

- 선택자를 입력하는 부분에 적용하려는 태그의 이름을 입력

```css
/*<h1>은 글자색이 빨강*/
h1 {
  color: red;
}
/*<p>는 글자색이 파랑*/
p {
  color: blue;
}
```

```html
<h1>제목1</h1> <!--red-->
<h1>제목2</h1> <!--red-->
<p>본문1</p> <!--blue-->
<p>본문2</p> <!--blue-->

```



### 3-2. 클래스(Class)

- 태그에 특정한 별칭을 부여
  - 해당 별칭을 가진 요소 혹은 요소들에만 접근하는 것이 가능
  - 여러 개의 클래스를 태그에 부여할 수 있으며, 각 클래스는 공백으로 구분
- `.클래스명`의 형태로 클래스 선택자를 사용
  - `.`은 해당 선택자가 클래스 선택자임을 의미
  - 기호를 누락할 경우, 같은 이름의 태그를 의미하게 되므로 꼼꼼한 작성이 필요

```css
/*class="title"은 글자색이 빨강*/
.title {
  color: red;
}
/*class="main-text"는 글자색이 파랑*/
.main-text {
  color: blue;
}
```

```html
<h1 class="title">제목1</h1> <!--red-->
<h1>제목2</h1>
<p class="main-text">본문1</p> <!--blue-->
<p>본문2</p>
```



## 4. 속성(Properties) Cont.

### 4-1. 크기

#### 4-1-1. width

- 요소의 **가로 너비**를 지정
- 단위는 `px`(pixels)을 사용

```css
div {
  width: 300px;
  요소가로너비: 너비값;
}
```



#### 4-1-2. height

- 요소의 **세로 너비**를 지정
- 단위는 `px`(pixels)을 사용

```css
div {
  height: 150px;
  요소세로너비: 너비값;
}
```



#### 4-1-3. font-size

- 요소 **내용(Text)의 글자 크기**를 지정
  - 대부분의 브라우저에서 기본값이 16px로 고정되어 있음

- 단위는 `px`(pixels)을 사용

```css
div {
  font-size: 16px;
  글자크기: 크기값;
}
```



### 4-2. 여백

#### 4-2-1. margin

- `margin-(top, left, bottom, right)`를 통해 한 방향씩 여백을 지정할 수도 있음
  - `margin`은 단축 속성, `margin-(top, left, bottom, right)`은 개별 속성이라고 함

- 요소의 **바깥 여백**을 지정
- 요소와 요소 사이의 여백(거리, 공간)을 생성할 때 사용

```css
div {
  margin: 20px;
  요소바깥여백: 여백값;
}

div {
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  margin-left: 20px;
  요소바깥여백-위쪽: 여백값;
  요소바깥여백-오른쪽: 여백값;
  요소바깥여백-아래쪽: 여백값;
  요소바깥여백-왼쪽: 여백값;
}
```



#### 4-2-2. padding

- 단축 속성
  - `padding-(top, left, bottom, right)`를 통해 한 방향씩 여백을 지정할 수도 있음

- 요소의 **내부 여백**을 지정
- 자식 요소를 감싸는 여백을 생성할 때 사용
  - 요소 안에 여백이 생기기 때문에, 여백이 늘어난 만큼 요소 자체의 크기가 커지게 됨

```css
div {
  padding: 20px;
  요소내부여백: 여백값;
}
```

```css
div {
  padding-top: 20px;
  padding-right: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
  요소내부여백-위쪽: 여백값;
  요소내부여백-오른쪽: 여백값;
  요소내부여백-아래쪽: 여백값;
  요소내부여백-왼쪽: 여백값;
}
```



### 4-3. 색상

#### 4-3-1. color

- 요소 **내용(Text)의 글자 색상**을 지정
  - `font-color`, `text-color` 등의 속성은 존재하지 않음

```css
div {
  color: red;
  글자색상: 빨강;
}
```



#### 4-3-2. background

- 단축 속성

- 요소의 **배경 색상**을 지정
- `color`는 글자의 색만 지정할 수 있으며, 요소의 색은 `background-color`로 변경

```css
div {
  background-color: red;
  요소배경: 빨강;
}
```

