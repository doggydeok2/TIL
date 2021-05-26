# HTML 요소-주요 범위 & 메타데이터

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 



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
