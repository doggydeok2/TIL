# HTML 요소-전역 속성, 기타

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. 전역 속성(Global Attributes)

- 모든 HTML 요소에서, 공통적으로 사용 가능한 속성



### 1-1. CLASS

- 공백으로 구분된, 요소의 별칭을 지정
  - 하나의 요소에 여러 클래스를 적용할 수 있음
  - 하나의 클래스를 여러 요소에 적용할 수 있음
- CSS 또는 JavaScript의 요소 선택기(CSS 선택자, GetElementsByClassName, QuerySelectorAll 등)를 통해 접근



### 1-2. ID

- 문서에서 고유한 식별자를 정의
  - 문서 내에서 고유해야 함
- CSS 또는 JavaScript의 요소 선택기(CSS 선택자, GetElementsById, QuerySelectorAll 등)을 통해 접근



### 1-3. STYLE

- 요소에 적용할 CSS를 선언



### 1-4. TITLE

- 요소의 정보(설명)를 지정
- 해당 요소에 커서를 대면, 작성한 `title` 속성값이 출력



### 1-5. LANG

- 요소의 언어([ISO 639-1](https://ko.wikipedia.org/wiki/ISO_639-1_%EC%BD%94%EB%93%9C_%EB%AA%A9%EB%A1%9D))를 지정

- 대부분의 경우 `<html>`에서 사용
  - 문서 내에서 적용되는 언어가 하나인 경우가 대다수이기 때문
  - 가급적 `<html>`에서만 한 번 선언하고 넘어가는 것을 권장



### 1-6. DATA-*

- 사용자가 정의하는, 데이터 속성을 지정
  - 데이터는 공백을 `-`로 대체(대시 표기)하며, JavaScript에서는 `-$`를 대문자로 치환해(카멜 표기) 작성
- HTML에, JavaScript에서 이용할 수 있는 데이터(정보)를 저장하는 용도로 사용

```html
<div id="me" data-my-name="Heropy" data-my-age="851">Heropy</div>

<script>
  const $me = document.getElementById('me');
  console.log($me.dataset.myName); // "Heropy"
  console.log($me.dataset.myAge); // "851"
</script>
```



### 1-7. DRAGGABLE

- 요소가 [Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)를 사용 가능한지 여부를 지정
- 속성을 작성하지 않을 시, 브라우저가 드래그 가능 여부를 판단하는 `auto` 상태가 됨



### 1-8. HIDDEN

- 요소를 숨김

```html
<form id="hidden-form" action="/form-action" hidden>
  <input type="text" name="id" value="doggy">
</form>
<button form="hidden-form" type="submit">전송</button>
```



### 1-9. TABINDEX

- `Tab` 키를 이용해, 요소를 순차적으로 포커스 탐색할 순서를 지정
  - [대화형 콘텐츠](https://developer.mozilla.org/ko/docs/Web/Guide/HTML/Content_categories#%EB%8C%80%ED%99%94%ED%98%95_%EC%BD%98%ED%85%90%EC%B8%A0)(`<a>`, `<img>`, `<input>`)는, 기본적으로 코드 순서대로 탭 순서가 지정
  - 비대화형 콘텐츠에 `tabindex="0"`을 지정하여, 대화형 콘텐츠와 같이 탭 순서를 사용
  - `tabindex=="-1"`을 통해, 포커스는 가능하지만 탭 순서에서 제외시킬 수 있음
  - `tabindex="1"` 이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않음
    - HTML 순서대로 탭 이동이 가능하게 둬라



## 2. 절대 경로와 상대 경로

### 2-1. 상대 경로

- 경로를 탐색하는 현재 파일의 위치에서부터, 목표한 파일의 위치를 찾아가는 방법
- `./`(현재 위치, 생략 가능), `../`(상위 위치)를 활용해 목표에 접근



### 2-2. 절대 경로

- 경로를 탐색하는 현재 파일의 위치와 무관하게, 목표한 파일의 절대적인 위치를 찾아가는 방법

- `https://`, `/`(만드는 문서가 절대 경로 내에 있는 경우, 도메인 주소를 생략)를 활용해 목표에 접근



## 3. 주석(Comment)

- 문서를 읽는 사용자를 위한, 코드에 대한 해석이나 설명 등의 메모
- HTML에서는, `<!-- -->` 내에 텍스트를 기입해 주석 처리하여 사용
  - CSS는 `/* */`, JavaScript에서는 `//`(한 줄) 및 `/* */`(여러 줄)를 통해 해당 줄을 주석 처리
  - 단축키 `Ctrl` + `/` 혹은 `cmd` + `/`를 통해 주석 처리할 수 있으니, 단축키를 활용 



## 4. 특수 기호(Entities)

- HTML 명령으로 동작하는 텍스트 등을, 특수 기호로 출력하고 싶을 때 사용
- [HTML Entity List](https://www.freeformatter.com/html-entities.html)에서 필요한 기호를 검색해 사용

```html
Hello&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;world!

<h1>
  &lt;div&gt;&lt;/div&gt;
</h1>
```

