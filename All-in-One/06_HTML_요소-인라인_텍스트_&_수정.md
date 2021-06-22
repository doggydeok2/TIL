# HTML 요소-인라인 텍스트 & 수정

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. 인라인 텍스트

### 1-1. A

- 다른 페이지, 같은 페이지, 파일, 이메일, 전화번호 등 다른 URL로 연결할 수 있는 하이퍼링크를 설정
  - 같은 페이지로 이동하는 경우, `href="#{id}"`의 형태로 속성을 작성
  - 위 경우 a tag를 클릭 시, 이동과 함께 브라우저 주소에도 `#{id}`가 추가됨
- 버튼의 형식으로 많이 사용함
  - `<a>` 는 inline 요소이므로 가로와 세로 크기의 설정이 불가능
  - 사용 추세에 따라 `display: block`을 통한 CSS 설정 후 사용하는 편

- `download`
  - 이 요소는 리소스를 다운로드하는 용도임을 명시
  - 링크를 통해 다운로드를 받게 해주는 것은 아님
- `href`
  - 링크 URL을 명시
  - HTML5에서 선택 속성으로 변경되었으나, 필수 속성처럼 활용
- `hreflang`
  - 링크 URL의 언어를 `ko`, `en` 등으로 명시
  - 자주 사용되는 속성은 아님
- `rel`
  - 현재 문서와 링크 URL 간 관계를 명시
  - `license`, `prev`, `next` 등
- `target`
  - 링크 URL의 표시 위치
    - 현재 페이지, 새로운 탭 등
  - `_self`(기본 ,현재 창), `_blank`(새로운 탭)

- `type`
  - 링크 URL의 MIME 타입을 설정
  - 타입이 자동으로 형성되므로, 잘 사용하는 속성은 아님



### 1-2. ABBR

- 약어를 지정
  - `title` 속성을 사용해 전체 글자나 설명을 제공

```html
Using<abbr title="HyperText Markup Language">HTML</abbr> is fun and easy!
```



### 1-3. B

- 문체가 다른 글자의 범위를 설정
  - 특별한 의미를 가지지 않음(Bring Attention)
  - 읽기 흐름에 도움을 주는 용도로 사용
  - 다른 문체 태그들이 적합하지 않은 경우, 마지막 수단으로 사용
  - 기본적으로, 글자가 두껍게(Bold) 표시됨



### 1-4. MARK

- 사용자의 관심을 끌기 위해, 하이라이팅할 때 사용
  - Mark Text, 형광펜을 사용하는 느낌으로 사용
  - 글자 배경이 노란색(Yellow)으로 표시됨

- 의미보다 시각적인 요소에 특화
  - 노란색 배경을 위해 사용하는 경우가 있음
  - CSS로 해결할 수 있는 부분이니 사용자의 선택에 따름



### 1-5. EM

- 단순한 강조(Emphasis)를 표시
  - 범위 내 텍스트에 강세를 주어, 사용자에게 강조하는 용도
  - 정보통신보조기기 등에서 구두 강조로 발음됨
- 중첩이 가능
  - 중첩될수록 강조의 의미가 강해짐

- 기본적으로, 이탤릭(Italic)체로 표시됨



### 1-6. STRONG

- 의미의 중요성을 나타내기 위해 사용
  - 중요성, 심각성, 긴급성이 있는 부분에 사용
- 기본적으로, 글자가 두껍게(Bold) 표시됨
  - `<b>`와 형태가 같으므로, 추가적인 CSS를 통해 혼동을 방지함



### 1-7. I

- `<em`, `<strong>`, `<mark>`, `<cite>`, `<dfn>` 등으로 표현할 수 없는, 적합한 의미가 아닌 경우 사용
  - 평범한 글자와 구분(아이콘, 특수기호 등을 사용할 때)하기 위해 사용
- 기본적으로, 이탤릭(Italic)체로 표시됨
  - `<em>`과 형태가 같으므로, 추가적인 CSS를 통해 혼동을 방지함



### 1-8. DFN

- 용어를 정의할 때 사용
  - `<dl><dt><dd>`는 다수의 용어를 나열할 때 사용하는 것이 적합
  - `<dfn>`은 하나의 용어를 정의할 때 사용
    - 문장 내에서 용어를 특정하는 용도

```html
<p>
  A <dfn id="def-validator">validator</dfn> is a program that checks for syntax errors in code or documents.
</p>
```



### 1-9. CITE

- 창작물에 대한 참조를 설정
  - 책 논문, 영화, TV 프로그램, 노래, 게임 등의 제목
- 기본적으로, 이탤릭체(Italic)로 표시됨

```html
<cite>The Scream</cite> by Edward Munch. Painted in 1893.
```



### 1-10. Q

- 짧은 인용문을 설정
  - Inline Quotation
  - 긴 인용문은 `<blockquote>`를 사용
- `cite`
  - 인용된 정보의 URL을 의미
  - 속성값으로 URL을 입력



### 1-11. U

- 밑줄이 있는 글자를 설정
  - `<a>`와 헷갈릴 수 있는 위치에선 사용하지 않도록 주의
- 순수하게 꾸미는 용도의 요소로 사용
- `<span style="text-decoration: underline;">`을 활용할 수 있을 경우, `<u>`의 사용을 권장하지 않음
  - `<u>`는 CSS를 통한 밑줄의 제어가 어려울 경우에 사용하는 태그



### 1-12. CODE

- 컴퓨터 코드 범위를 설정
- 기본적으로, 고정폭(MonospacE) 글꼴 계열로 표시됨

```html
<code>document.getElementById('id-value')</code> is a piece of computer code.
```



### 1-13. KBD

- 텍스트 입력 장치(키보드)에서 사용자 입력을 나타내는 텍스트 범위를 설정

```html
<p><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>K</kbd></p>
<kbd>ESC</kbd>
```



### 1-14. SUP, SUB

- 위 첨자(`<sup>`)와 아래 첨자(`<sub>`)를 설정

```html
X<sup>4</sup> + Y<sup>2</sup>
H<sub>2</sub>O
```



### 1-15. TIME

- 날짜나 시간을 나타내기 위한 목적으로 사용
- `datetime`
  - 유효한 날짜 문자를 의미
  - 속성값으로 Date를 입력
    - YYYY-MM-DD, hh:mm 등

```html
<p>
  The Cure will be celebrating their 40th anniversary on <time datetime="2018-07-07">July 7</time> in London's Hyde Park.
</p>
```



### 1-16. SPAN

- 아무것도 나타내지 않는 콘텐츠 영역을 설정
  - 블록 요소인 `<div>`와 유사한 인라인 요소

- 일부를 묶어 CSS나 JavaScript를 적용할 때 주로 사용



### 1-17. BR

- 줄바꿈을 설정(break)
- 빈  태그
- 줄 간격을 넓히는 용도로, `<br/>`을 여러 번 사용하지 말 것
  - HTML은 구조를 잡는 것임을 명심하고, CSS를 활용할 것
  - 줄 간격은 `<p>` 등의 줄 높이를 설정하여 만들어내야 함



## 2. 수정

### 2-1. DEL

- 삭제된 텍스트의 범위를 지정
- `cite`
  - 변경을 설명하는 리소스의 URI
  - 속성값으로 URI를 입력
- `datetime`
  - 변경이 일어난 유효한 날짜 문자
  - 속성값으로 Date를 입력



### 2-2. INS

- 새로 추가된 텍스트의 범위를 지정
- `cite`, `datetime` 속성은 `<del>`과 동일

