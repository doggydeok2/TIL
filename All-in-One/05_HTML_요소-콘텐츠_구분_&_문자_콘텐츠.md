# HTML 요소-콘텐츠 구분 & 문자 콘텐츠

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. BODY 내 구조 개념

- `<div>` 태그만을 사용한 코드가, 동작이나 구조에 있어 문제를 나타내는 것은 아님

- 다만 다양한 의미를 가진 태그들을 활용함으로써, 보다 유의미하고 직관적인 코드를 작성할 수 있음
  - 시맨틱 태그의 사용을 통해, 브라우저나 정보 보조 기구 등의 



## 2. 콘텐츠 구분

### 2-1. HEADER

- 소개나 탐색을 돕는, 주로 화면 상단에 위치한 콘텐츠
- 주로 제목, 로고, 검색 폼, 작성자 이름 등의 요소가 포함

- `<header>`, `<footer>` 태그를 `<header>` 태그의 자손으로 가질 수 없음
- `<address>`, `<footer>`, `<header>` 태그의 자손으로 `<header>` 태그가 올 수 없음



### 2-2. FOOTER

- 작성자 구획, 저작권 데이터, 관련 문서 링크 등의 정보를 포함하는, 주로 화면 하단에 위치한 콘텐츠

- `<header>`, `<footer>` 태그를 `<footer>` 태그의 자손으로 가질 수 없음
- `<address>`, `<header>`, `<footer>` 태그의 자손으로 `<footer>` 태그가 올 수 없음



### 2-3. H

- 문서의 제목을 구현

- `<h1>`부터 `<h6>`까지 6단계가 존재
  - `<h1>` 태그가 가장 큰 주제를, `<h6>` 태그가 가장 작은 주제를 의미
  - **제목 폰트의 크기를 줄이기 위해 낮은 단계를 사용하지 말 것**
    - HTML은 문서의 구조를 표현하므로, 크기의 조절이 HTML 태그 변경의 목적으로 부적합
    - 브라우저마다 각 태그의 글자 크기가 다를 수 있으니, CSS의 `font-size`를 통해 변경할 것

- 단계를 건너뛰지 말고, `<h1>`부터 `<h6>`까지 순차적으로 사용할 것
  - 브라우저 등이 정보를 수집함에 있어, 빈 구간이 문제를 일으킬 수 있음
- `<h1>` 태그는 문서에서 단 한 번만 사용할 것

```html
<h1>제목1</h1>
<h2>제목2</h2>
<h3>제목3</h3>
<h4>제목4</h4>
<h5>제목5</h5>
<h6>제목6</h6>
```

#### 2-3-1. Content Label

- 한 페이지에 다수의 구획이 있을 경우, 페이지 레이아웃의 파악을 위해 사용
- `aria-labelledby`와 `id` 속성을 이용해 각 구획의 목적을 설명하는 레이블을 붙임

```html
  <header>
    <nav aria-labelledby="primary-navigation">
      <h2 id="primary-navigation">Primary navigation</h2>
      <p>item1</p>
    </nav>
  </header>
  <footer>
    <nav aria-labelledby="footer-navigation">
      <h2 id="footer-navigation">Footer navigation</h2>
      <p>item2</p>
    </nav>
  </footer>
```



### 2-4. MAIN

- 문서나 앱 `<body>`의 주요 콘텐츠를 나타냄
  - 블로그의 핵심 포스트 등, 문서의 핵심 기능을 의미
  - 온전한 정보 제공용으로, 페이지의 개념적 구조를 변경하지 않음
- 문서에 하나만 존재해야 함
  - 여럿을 사용할 땐, `hidden` 등을 통해 매 상황에 하나의 `<main>`만 출력될 수 있도록 할 것



### 2-5. ARTICLE

- 독립적으로 구분되거나, 재사용 가능한 영역을 설정
- 보통 `<h1>~<h6>`를 포함하여 식별
- 작성일자와 시간을 `<time>`의 `datetime` 속성으로 작성
- 제목을 포함하는 유의미한 태그로, `<h>` 태그를 사용함에 있어 `<div>`와의 차이가 있음



### 2-6. SECTION

- 문서의 일반적인 영역을 설정
  - 보다 다양한 곳에서 쓸 수 있는, 영역을 나누는 용도로 사용되는 태그
- 보통 `<h1>~<h6>`를 포함하여 식별

- 제목을 포함하는 유의미한 태그로, `<h>` 태그를 사용함에 있어 `<div>`와의 차이가 있음



### 2-7. ASIDE

- 문서의 별도 콘텐츠를 설정
  - 광고, 기타 링크 등의 사이드바(Side bar)에 사용
- 문서 전체 콘텐츠와 구분되는 내용들이 주로 들어감



### 2-8. NAV

- 다른 페이지 링크를 제공하는 영역을 설정
  - Navigation의 약자
  - 메뉴(Home, About, Contact, ...), 목차, 색인 등을 설정

- 메뉴를 묶을 경우엔, `<ol>` 태그나 `<ul>` 태그를 사용하는 경우가 많음

```html
<body>
  <header>
    <nav>
      <ul>
        <li>Shots</li>
        <li>Designers</li>
        <li>Teams</li>
        <li>Community</li>
        <li>Jobs</li>
        <li>Hiring</li>
      </ul>
    </nav>
  </header>
</body>
```



### 2-9. ADDRESS

- 연락처 정보를 제공하기 위해 포함하여 사용
  - 이메일, 전화번호, 주소 등
- `<body>`, `<article>`, `<footer>` 등에서 사용



### 2-10. DIV

- 아무것도 나타내지 않는 콘텐츠 영역을 설정
  - 꾸미는 목적으로 사용
    - 주로, 특정 영역에 CSS나 JS를 통한 제어를 하기 위함



## 3. 문자 콘텐츠

### 3-1. OL, UL, LI

- 목록을 만들 때 사용
- 목록에 순서가 필요할 경우, 정렬된 목록을 나타내는 `<ol>` 태그와 `<li>` 태그를 묶어 사용
  - 항목 순서는 순서 외에 중요도를 의미할 수도 있음
- 목록에 순서가 필요하지 않다면, `<ul>` 태그와 `<li>` 태그를 묶어 사용
- `<ol>` 및 `<ul>` 태그는 자식으로 `<li>`만 포함할 수 있음
- `<li>` 태그는 `<ol>` 태그나 `<ul>` 태그의 자식으로 포함되어야 하며, 단독으로 사용할 수 없음

- `<ol>` 속성
  - `start`
    - 항목에 매겨지는 번호의 시작 값을 설정
  - `reversed`
    - 순서를 역순으로 출력
    - 번호만 역순으로 매김
  - `type`
    - `A`, `a`, `I`, `i`, `1` 등 번호 유형을 설정
- `<li>` 속성
  - `value`
    - 항목의 순서를 설정
    - 이하 항목들의 순서 또한 재지정
    - 작성한 `<li>`의 순서가 변경되는 것은 아님

```html
<body>
  <ol type="I" reversed>
    <li value="7">
      Apple
      <ol start="5">
        <li>Apple</li>
        <li>Banana</li>
        <li>Mango</li>
      </ol>
    </li>
    <li value="99">Banana</li>
    <li>Mango</li>
  </ol>
</body>
```



### 3-2. DL, DT, DD

- 용어(`<dt>`)와 정의(`<dd>`) 쌍들의 영역(`<dl>`)을 설정
- 키(key)/값(value) 형태의 표시에 유용
- `<dl>` 태그 내에는 `<dd>`, `<dt>` 태그만 존재해야 함
  - 스타일링의 까다로움 등으로 인해, `<ul(ol)>`, `<li>` 로 대체
  - `<dfn>`와 `<p>` 태그를 `<dt>`와 `<dd>`의 대체로 사용해 `<li>` 안에 삽입하는 등의 방식을 사용
  - `<dfn>` 태그
    - 현재 맥락이나 문장에서 정의하는 용어를 나타냄
    - 가장 가까운 `<p>`, `<dt><dd>`, `<section>` 조상 요소를 용어 정의로 간주

```html
<dl>
  <dt>Coffee</dt>
  <dd>Coffee is a brewed drink prepared from roasted coffee beans, the seeds of berries from certain Coffea species.</dd>
  <dt>Milk</dt>
  <dd>Milk is a nutrient-rich, white liquid food produced by the mammary glands of mammals.</dd>
</dl>

<!-- 대체 -->
<ul>
  <li>
    <dfn>Coffee</dfn>
    <p><dfn>Coffee</dfn> is a brewed drink prepared from roasted coffee beans, the seeds of berries from certain Coffea species.</p>
  </li>
  <li>
    <dfn>Milk</dfn>
    <p>Milk is a nutrient-rich, white liquid food produced by the mammary glands of mammals.</p>
  </li>
</ul>
```



### 3-3. P, HR

- `<p>`
  - 하나의 문장, 문단, 단락 등을 설정
  - 일반적으로, 정보통신보조기기 등이 다음 `<p>`로 넘어갈 수 있는 단축키를 제공하므로, 자주 사용
  - 태그 내에서, 코드 상의 enter는 브라우저 상에 줄바꿈으로 출력되지 않음
    - 이를 원할 경우 각 문단을 block 요소로 묶어주거나, `<br/>` 태그 등을 활용

- `<hr/>`
  - 주제에 의한 문단의 분리를 위해 설정
  - Horizontal Rule
  - 대부분의 경우 수평선(border)으로 표시되나, 시각적 관점이 아닌 의미적 관점으로 사용해야 함
    - 분리를 하다 보니 수평선이 들어가는 것이며, CSS를 통해 수평선의 변경이 가능
    - 수평선을 넣기 위해 태그를 사용하는 대신, CSS를 활용할 것
    - 요소는 사각형으로, '선'으로 활용하기 위해선, CSS를 통해 위/아래나 좌/우 중 하나만 사용함



### 3-4. PRE

- 서식이 미리 지정된 텍스트를 설정(Preformatted Text)
  - 텍스트의 공백과 줄바꿈을 유지하여 표시할 수 있음
    - 원하는 서식, 양식을 출력 가능
    - 코드의 가독성을 위한 tab 등도 인식이 되므로, 코드 작성에 유의
  - 기본적으로, Monospace 글꼴 계열로 표시
    - 모든 글자가 같은 너비를 가짐

```html
<body>
  <div>
    동해물과     백두산이 마르고 닳도록
    하느님이 보우하사 우리나라 만세.
    무궁화 삼천리 화려강산
    대한 사람, 대한으로 길이 보전하세.
  </div>
<pre>동해물과     백두산이 마르고 닳도록
하느님이 보우하사 우리나라 만세.
무궁화 삼천리 화려강산
대한 사람, 대한으로 길이 보전하세.</pre>
</body>
```



### 3-5. BLOCKQUOTE

- 인용문을 설정(Block Quotation)
- `cite`
  - 인용된 정보의 URL을 의미
  - 값으로 URL을 작성

