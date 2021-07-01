# CSS 실습 환경

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 



## 1. CSS Reset

- 다양한 브라우저를 사용하는 사용자들을 고려한, 웹 사이트 제작을 위함
  - 각 HTML 태그에 대한 출력 방식이 표준화되어 있지 않음
  - 브라우저마다 동일한 서비스를 제공하기 위해, 브라우저 기본 CSS를 제거할 필요가 있음

```css
body {
  margin: 0;
  padding: 0;
}
```



### 1-1. Reset-CSS

>https://www.jsdelivr.com/package/npm/reset-css

- [reset-css CDN](https://www.jsdelivr.com/package/npm/reset-css) 등을 HTML `<link>`로 불러옴으로써, 간편한 CSS 리셋이 가능
  - `<link>` 태그 중 가장 위에 위치해야, 다른 CSS가 적용되기 전에 리셋이 가능
  - 다른 CSS의 적용 후 위 CDN을 사용 시, 작성한 CSS 일부가 미적용될 수 있음

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">
```



## 2. Codepen

> https://codepen.io/

- 온라인에서 HTML / CSS / JavaScript 코드를 작성, 화면 미리보기 및 저장 등의 기능을 제공
  - HTML은 `<body>`로 감싸져있는 상태로 제공

- HTML / CSS / JavaScript마다 각각의 설정 제공
  - CSS Reset 등도 자체적으로 제공



## 3. Emmet

- HTML과 CSS를 용이하게 작성하게 해주는 툴
- 많은 IDE들이 Emmet 문법을 내장하고 있음
  - 위의 Codepen 또한 Emmet 사용 가능
- 약어를 입력 후 `tab` 키를 눌러 툴을 동작



### 3-1. HTML

- CSS 선택자만 입력하면(`.box` `enter`), 해당하는 class의 `<div>` 태그가 작성됨

```html
<div class="box"></div>
```

- 태그명과 CSS 선택자를 입력하면(`ul.list`) 해당하는 태그에 class가 입력되어 작성됨

```html
<ul class="list"></ul>
```

- CSS의 자식 선택자 형태로 입력하면 태그의 자식으로 해당 태그가 생성됨
- `*N`을 통해 N개의 동일한 태그를 생성할 수 있음
- `{text}`를 통해, 태그의 내용을 삽입할 수 있음
- (`.container>ul.list>li.list-item*10>a{list$}`)

```html
  <div class="container">
    <ul class="list">
      <li class="list-item"><a href="">list1</a></li>
      <li class="list-item"><a href="">list2</a></li>
      <li class="list-item"><a href="">list3</a></li>
      <li class="list-item"><a href="">list4</a></li>
      <li class="list-item"><a href="">list5</a></li>
      <li class="list-item"><a href="">list6</a></li>
      <li class="list-item"><a href="">list7</a></li>
      <li class="list-item"><a href="">list8</a></li>
      <li class="list-item"><a href="">list9</a></li>
      <li class="list-item"><a href="">list10</a></li>
    </ul>
  </div>
```



### 3-2. CSS

- width/height는 w/h의 약어로 사용할 수 있음
- 픽셀 단위를 사용하고 싶지 않은 경우, 단위를 직접 명시
- `w:100`, `h:100%`

```css
width: 100px;
height: 100%;
```

