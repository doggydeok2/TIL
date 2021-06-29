# HTML 요소-표 콘텐츠 & 양식

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online. 
>
> https://heropy.blog/2019/05/26/html-elements/



## 1. 표 콘텐츠

### 1-1. TABLE, TR, TH, TD

- 데이터 표(`<table>`)의 행(줄, `<tr>`)과 열(칸, 셀(Cell), `<th>`, `<td>`)을 생성
  - `<table>`에 행 수만큼 `<tr>`을 선언하고, 각 행마다 열 수만큼 `<th>`나 `<td>`를 선언
  - CSS를 통해 표 테두리(`border`, `border-collpase`) 등을 추가
- 레이아웃을 위해 `<table>`을 쓰는, '테이블 코딩'을 하지 말 것
  - 표를 만드는 용도로만 사용하라!



#### 1-1-1. TH

- '머리글 칸'을 지정
- `abbr`
  - 열에 대한 간단한 설명(약어)
  - 표가 변경되지는 않으며, 참고 사항으로 작성
- `headers`
  - 관련된 하나 이상의, 다른 머리글 칸(`<th>`) `id` 속성 값
  - 해당 칸이 `id` 개념 칸의 하위 종목임을 표기
  - 표의 사용도가 시각적인 표현에만 중점이 있다면, 모든 셀에 사용할 필요는 없음
- `colspan`
  - 병합하려는 열의 수
  - 작성 위치부터 우측으로 칸 수를 셈
- `rowspan`
  - 병합하려는 행의 수
  - 작성 위치부터 아래로 칸 수를 셈
- `scope`
  - 자신이 누구의 '머리글 칸'인지 명시
  - `col`: 자신의 열, `colgroup`: 모든 열, `row`: 자신의 행, `rowgroup`: 모든 행, `auto`(기본값)



#### 1-1-2. TD

- '일반 칸'을 지정
- `headers`
  - 관련된 하나 이상의, 다른 머리글 칸(`<th>`) `id` 속성 값
  - 해당 칸이 `id` 개념 칸의 하위 종목임을 표기
  - 표의 사용도가 시각적인 표현에만 중점이 있다면, 모든 셀에 사용할 필요는 없음
- `colspan`, `rowspan`
  - 병합하려는 열/행의 수
  - 작성 위치부터 우측으로/아래로 칸 수를 셈



### 1-2. CAPTION

- 표의 제목을 설정
  - 열리는 `<table>` 바로 다음에 작성해야 함
  - `<table>` 하나당 하나의 `<caption>`만 사용 가능

```html
<table>
  <caption>데이터 타입과 값</caption>
  <tr>
    ...
  </tr>
  ...
</table>
```



### 1-3. COLGROUP, COL

- 표의 열들을 공통적으로 정의하는 컬럼(`<col>`) 및 그의 집합(`<colgroup>`)
  - 첫 `<tr>` 위에 작성하는 것이 일반적
  - `<col>` 수는 열의 수와 동일하며, `<col>` 일부 혹은 전체를 `<colgroup>`으로 묶어 사용할 수 있음
- 열 전체를 제어(CSS 적용 등)할 때 사용
- `span`
  - 함께 제어하려는 열의 수



### 1-4. THEAD, TBODY, TFOOT

- 표의 머리글(`<thead>`), 본문(`<tbody>`), 바닥글(`<tfoot>`)을 지정
  - 기본적으로, 테이블의 레이아웃에 영향을 주지 않음



## 2. 양식

### 2-1. FORM

- 웹 서버에 정보를 제출하기 위한, 양식 범위를 정의

  - `<form>`은 다른 `<form>`을 자식 요소로 포함할 수 없음

- 지정한 범위 내의 입력 정보들을, 특정한 페이지나 주소로 전송하기 위해 사용

- `action`

  - 전송할 정보를 처리할 웹페이지의 URL

- `autocomplete`

  - 사용자가 이전에 입력한 값으로, 자동 완성 기능을 사용할 것인지 여부
  - `on`(기본값), `off`

- `method`

  - 서버로 전송할 HTTP 방식

  - `GET`(기본값), `POST`
    - GET 방식은, URL에 전송하고자 하는 정보가 적혀있는 것이 특징
    - POST 방식은, URL에 정보를 표시하지 않으며 별도의 formdata를 통해 전송
    - POST 방식도 데이터가 숨겨지진 않으므로, 필요 시 도의 암호화를 하는 것이 일반적

- `name`

  - 고유한 양식의 이름
  - 필수는 아니나, 다른 `<form>`과 동시에 특정 정보를 제출할 때 사용하면 유용

- `novalidate`

  - 서버로 데이터를 전송할 때, 양식 데이터의 유효성을 검사하지 않도록 지정
  - 예로, email 양식에 '@'를 사용하지 않아도 전송되게끔 하는 것

- `target`

  - 서버로 전송 후, 응답받을 방식을 지정
  - `<a>` 태그의 `target` 속성과 유사
    - `<form>`을 제출한 후 해당 URL이 열릴 때, 페이지를 출력하는 방식
  - `_self`(기본값), `_blank`



### 2-2. INPUT

- 사용자에게 입력 받을 데이터 양식
- 빈 태그
- `autocomplete`
  - 사용자가 이전에 입력한 값으로, 자동 완성 기능을 사용할 것인지 여부
  - `on`(기본값), `off`
- `autofocus`
  - 페이지가 로드될 때, 자동으로 포커스
  - 동시에 여럿을 포커싱할 수 없기에, **문서 내**에서 고유해야 함
- `checked`
  - 양식이 선택되었음을 표시
  - `type` 속성값이 `radio`, `checkbox`일 경우에만 사용 가능
- `form`
  - `<form>`의 `id` 속성값
  - 데이터 양식이 `<form>` 밖에 존재하는 특수한 상황에서 활용
- `name`
  - 양식의 이름
  - 서버로 데이터가 전송될 때, 데이터가 가지는 이름이 지정됨
  - 없을 시, 해당 양식의 데이터가 전송되지 않음
- `type`
  - 입력 받을 데이터의 종류
- 이외
  - `disabled`
    - 양식을 비활성화
    - 포커스되지 않음
  - `list`
    - 참조할 `<datalist>`의 `id` 속성값
  - `max`, `min`
    - 지정 가능한 최대/최소 값
    - `type` 속성값이 `number`일 경우 사용 가능
    - `min`과 `max`의 범위 설정에 오류가 없어야 함
  - `maxlength`
    - 입력 가능한 최대 문자 수
    - `type` 속성값이 `text`, `email`, `password`, `tel`, `url`일 경우 사용 가능
  - `multiple`
    - 둘 이상의 값을 입력할 수 있는지 여부
    - `type` 속성값이 `email`, `file`일 경우 사용 가능
    - `email`의 경우 `,`로 구분
  - `placeholder`
    - 사용자가 입력할 값의 힌트
    - 입력 칸에 작성되어 표시됨
  - `readonly`
    - 수정 불가한 읽기 전용
    - `disabled`와 달리, 포커스는 가능
  - `step`
    - 유효한 증감 숫자의 간격
    - `type` 속성값이 `number`, `range`일 경우 사용 가능
  - `src`, `alt`
    - 이미지의 URL / 이미지의 대체 텍스트
    - `type` 속성이 `image`일 경우 사용 가능
  - `value`
    - 양식의 초기 값



#### 2-2-1. 데이터 종류(Type)의 값(Values)

`type` 속성에 입력할 수 있는 값의 목록

- `button`: 일반 버튼. `<button>`처럼 사용
- `checkbox`: 체크박스
- `color`: 색상
- `email`: 이메일
- `file`: 파일
- `hidden`: `value` 속성으로 값을 지정한, 보이지 않으나 전송되는 양식
- `image`: 이미지 제출 버튼. `<img />`처럼 사용. `type="submit"`으로도 사용 가능
- `number`: 숫자
- `password`: 비밀. 가려지는 양식
- `radio`: 라디오 버튼. 같은 `name` 속성 그룹 내에서 하나만 선택 가능
- `range`: 범위 컨트롤. `min`, `max`, `step`, `value` 속성 사용
- `reset`: 초기화. 해당 `<form>` 범위 내 양식들에 적용
- `search`: 검색
- `submit`: 제출 버튼. 해당 `<form>` 범위 내 양식들에 적용
- `tel`: 전화번호
- `text`: 일반 텍스트
- `url`: 절대 URL



### 2-3. LABEL

- 라벨 가능 요소(`<button>`, `<input>`, `<progress>`, `<select>`, `<textarea>`)의 제목(Caption)
- 제목을 클릭 시, 라벨된 요소에 포커싱
- `for`
  - 참조할 라벨 가능 요소의 `id` 속성 값
  - 해당 라벨 가능 요소를, 참조하거나 콘텐츠로 포함

```html
<!-- 라벨 가능 요소를 참조 -->
<input type="checkbox" id="user-agreement" />
<label for="user-agreement">동의하십니까?</label>

<!-- 라벨 가능 요소를 포함 -->
<label><input type="checkbox" />동의하십니까?</label>
```



### 2-4. BUTTON

- 선택 가능한 버튼을 지정
  - `<input type="button">`으로 대체 가능하나, 보다 직관적
- `autofocus`, `disabled`, `form`, `name`, `type` 속성이 있으며, `<input>`의 해당 속성 동작과 동일

- 기본적으로 버튼은 아무 동작이 없으며, JavaScript 코드 등을 덧붙여 사용



### 2-5. TEXTAREA

- 여러 줄의 일반 텍스트 양식
- `rows`
  - 양식의 줄 수. 2줄이 기본값
  - 그 이상도 입력이 가능하나, 화면에는 설정한 만큼의 줄만 보이게 됨
- 이외 `autocomplete`, `autofocus`, `disabled`, `form`, `maxlength`, `name`, `placeholder`, `readonly` 속성이 있으며, `<input>`의 해당 속성 동작과 동일



### 2-6. FIELDSET, LEGEND

- 같은 목적의 양식을, 그룹화(`<fieldset>`)하여 제목(`<legend>`)을 지정
- `disabled`
  - 그룹 내 모든 양식 요소를 비활성화
- `form`
  - 그룹이 속할 하나 이상의 `<form>`의 `id` 속성값
- `name`
  - 그룹의 이름

```html
<form>
  <fieldset>
    <legend>Coffee Size</legend>
    <label>
        <input type="radio" name="size" value="tall" />
        Tall
    </label>
    <label>
        <input type="radio" name="size" value="grande" />
        Grande
    </label>
    <label>
        <input type="radio" name="size" value="venti" />
        Venti
    </label>
  </fieldset>
</form>
```



### 2-7. SELECT, DATALIST, OPTGROUP, OPTION

- 옵션(`<option>`, `<optgroup>`)의 선택 메뉴(`<select>`)나 자동완성(`<datalist>`)을 제공



#### 2-7-1. SELECT

- 옵션을 선택하는 메뉴
- `size`
  - 한 번에 볼 수 있는 행의 개수
  - 기본값은 0이며 이는 1과 동일하게 동작
- 외 `autocomplete`, `disabled`, `form`, `multiple`, `name` 속성 존재



#### 2-7-2. OPTGROUP

- `<option>`을 그룹화

- `label`
  - 옵션 그룹의 이름
  - 필수 속성
- `disabled`
  - 해당 옵션 그룹을 비활성화



#### 2-7-3. OPTION

- 선택 메뉴(`<select>`)나 자동완성(<`datalist>`)에서 사용될 옵션
  - 선택적 빈 태그로 사용 가능

- `label`
  - 표시될 옵션의 제목
  - 생략된 경우, 태그 내에 포함된 텍스트를 표시

- `value`
  - 선택됐을 때 값으로 사용할 정보
  - 생략된 경우, 태그 내에 포함된 텍스트를 사용

- `disabled`
  - 옵션을 비활성화
- `selected`
  - 옵션이 선택되었음을 표시



#### 2-7-4. DATALIST

- `<input>`에 미리 정의된 옵션을 지정하여 자동완성 기능을 제공하는 데 사용
  - `<input>`의 `list` 속성 바인딩
  - `<option>`을 포함하여 정의된 옵션을 지정

- JavaScript 없이 자동완성 기능을 제공할 수 있음
- `<datalist>`의 `id`와, `<input>`의 `list`가 동일해야 함

```html
<input type="text" list="fruits">

<datalist id="fruits">
  <option>Apple</option>
  <option>Orange</option>
  <option>Banana</option>
  <option>Mango</option>
  <option>Fineapple</option>
</datalist>
```



### 2-8. PROGRESS

- 작업의 완료 진행률을 표시
  - 로딩 바
- `max`
  - 작업의 총량을 숫자로 명시
- `value`
  - 작업의 진행량을 숫자로 명시
  - `max` 속성이 생략된 경우, 0 ~ 1 사이의 숫자여야 함

