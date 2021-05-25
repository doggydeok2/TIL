# 00. HTML & CSS 첫걸음 / 개요

> 패스트캠퍼스 프론트엔드 개발 올인원 패키지 with React Online.
>
> https://heropy.blog/2019/04/24/html-css-starter/



## 1. HTML, CSS 그리고 JavaScript

> https://html-css-js.com/

- 각각 여러 세부 종류가 있을 수 있겠지만 크게 세 가지로 구분할 수 있음
- 세 언어는 각각의 역할이 다름
  - 각 언어의 역할을 다른 언어가 대체하지 않도록 주의
  - 각 역할이 적저맇 수행되도록 구조적, 기술적으로 언어(코드)를 최적화시킬 필요가 있음

### 1-1. HTML(HyperText Markup Language)

- 페이지에 제목, 문단, 표, 이미지, 동영상 등을 정의하고 그 구조와 의미를 부여하는 정적 언어
- 웹의 구조를 담당하므로, 튼튼한 구조(Semantic)을 만드는 것에 집중

### 1-2. CSS(Cascading Style Sheeets)

- HTML, XML: 등의 마크업 언어가 실제 표시되는 색상, 크기, 폰트, 레이아웃 등을 지정해 콘텐츠 구조를 꾸며주는 정적 언어
- 웹의 시각적인 표현을 담당

### 1-3. JS(JavaScript)

- 콘텐츠를 바꾸고 움직이는 등 페이지를 동적으로 꾸며주는 역할을 하는 프로그래밍 언어
  - CSS 변화나 HTML 구조 변경 등 상황에 맞게 페이지가 바뀜
  - 만들어져 있는 것만을 출력하는 정적인 HTML, CSS와 차이가 있음
- HTML과 CSS를 동원해 그 역할을 담당할 수 있으나 성능적인 아쉬움이 존재
  - 되도록 동적 처리에 집중해 사용



## 2. 웹 표준과 웹 접근성

### 2-1. 웹 표준

- HTML, CSS, JS 등 W3C의 권고안에서 나온 '웹에서 사용되는 표준 기술이나 규칙'
- 표준 기술들을 기준으로 크롬, IE, 사파리 등 웹 브라우저들이 만들어짐
- 브라우저를 만드는 구글, MS, 애플 등 업체들이 W3C을 해석하는 과정에서의 차이나 새로운 기술 삽입([표준화 제정 단계](https://wit.nts-corp.com/2013/10/16/280)에 따른) 등으로 조금 다르게 구동되는 브라우저가 발생
  - 웹에 새로운 기술을 적용하고 싶을 때 검증 단계가 남아있다면 초안(WD: Working Draft)이나 후보권고안(CR: Candidate Recommendation)
  - 검증을 다 거쳐 웹에서 사용이 문제 없으리라 판단되면 권고안(REC: Recommendation)
  - 대부분의 브라우저가 권고안에 따라 만들어지므로 권고안에 해당되는 기술들만을 익히면 되는 것
- ActiveX, Flash 등은 특정 회사의 기술이며 표준화된 것이 아니므로 사라지는 추세

### 2-2. 크로스 브라우징

- 조금씩 다르게 구동되는 여러 브라우저에서 같은 화면 및 동작(UX: User eXperience)을 줄 수 있게끔 제작하는 기술 및 방법
- 대부분의 브라우저가 웹 표준을 준수해 제작됨

### 2-3. 웹 접근성

>[웹 접근성 연구소](https://www.wah.or.kr:444/Accessibility/define.asp)
>
>[한국형 웹 콘텐츠 접근성 지침 2.1](https://www.wah.or.kr:444/Participation/guide.asp)
>
>[웹 콘텐츠 제작 기법](https://www.wah.or.kr:444/Participation/technique.asp)

- 신체적, 환경적 조건에 제한이 있는 사용자를 포함한 모든 사용자들이 동등하게 접근할 수 있는 웹 콥텐츠를 제작하는 방법
  - 영상에 자막을 넣기
  - 키보드나 마우스만을 통해 웹을 이용할 수 있게 하기
  - 이미지에 대체 텍스트를 제공하기 등



## 3. VS code EXTENSIONS

### 3-1. Korean Language Pack for Visual Studio Code

- VS Code 한글 패치
- 설치 후 재부팅하여 적용

### 3-2. Beautify

- 코드 가독성을 위해 코드 스타일을 정리해줌

- 파일 - 기본 설정 - 바로가기 키
  - HookyQR.beautify 에 단축키를 지정
  - HookyQR.beautifyFile은 모든 파일의 스타일을 재정의하므로 원치 않은 변경이 생길 수 있어 권장하지 않음
  - Ctrl(Cmd) + Alt + L 권장

### 3-3. Live Server

- 작성한 HTML, CSS, JS 코드를 브라우저에서 확인할 수 있음
- 하단 바의 Go Live 버튼 및 Port 버튼을 통해 서버를 키고 끌 수 있음



## 4. VS code Keyboard Shortcut

- `"`를 사용하여 키 바인딩을 검색할 수 있음
  - `""`로 닫으면 정확한 검색을 요구하게 되므로 닫지 않고 검색하는 것을 추천

### 4-1. 자주 쓰는 단축키

- 찾기(검색)
  
  - Windows: `Ctrl + F`, MacOS: `Cmd + F`
- 찾기(검색) 및 바꾸기(대체)
  
  - Windows: `Ctrl + H`, MacOS: `Cmd + Opt(Alt) + F`
- 들여쓰기
  
  - Windows, MacOS: `Tab`
- 내어쓰기
  
  - Windows, MacOS: `Shift + Tab`
- 편집기 분할(백슬래쉬)
  
  - Windows: `Ctrl + \`, MacOS: `Cmd + \`
- `숫자`번째 분할된 편집기 그룹에 포커스
  
  - Windows: `Ctrl + 숫자`, MacOS: `Cmd + 숫자`
- 편집기 닫기
  
- Windows: `Ctrl + W`, MacOS: `Cmd + W`
  
- 약어로 랩핑(Wrap)

  - 코드를 태그로 감쌀 때 사용

  1. 랩핑할 코드 선택(블록)
  2. 모든 명령 표시 실행
     - Windows: `Ctrl + Shift + P`, MacOS: `Cmd + Shift + P`
  3. `Emmet: Wrap with Abbreviation`를 입력하거나 목록에서 선택(`Enter`)
  4. `div`, `span` 등 Emmet 문법(ex: `.wrapper`, `span.bold`)을 입력
  5. 완료(`Enter`)



## 5. Image - Bitmap, Vector

- 이미지(그래픽)는 크게 비트맵과 벡터로 구분

### 5-1. 비트맵(Bitmap)

- 각 픽셀이 모여 만들어진 저옵의 집합으로 레스터(Raster) 이미지라고도 함
- 픽셀 단위로 화면에 렌더링
  - 렌더링: 컴퓨터가 화면에 그림을 그려 우리가 보게끔 하는 것
- jpg, png, gif, webp 등 일반적으로 사용하는 대부분의 이미지의 형식
- 포토샵 등의 툴로 편집 가능

#### 5-1-1. JPG, JPEG(Joint Photographic coding (Experts) Group)

- Full-Color, Gray-Scale의 압축을 위해 만들어진 형식
- 강력한 압축률(적은 용량)로 사진 및 예술 분야에서 많이 사용
- 특징
  - 손실 압축
    - 원본 파일을 jpg로 확장자 변환하여 덮어씌우는 것을 권장하지 않음
  - 뛰어난 표현 색상도(24비트, 약 1600만 색상)로 고해상도 표시장치에 적합
  - 이미지의 품질과 용량을 쉽게 조절 가능
  - 가장 널리 쓰이는 이미지 포맷

#### 5-1-2. PNG(Portable Network Graphics)

- GIF의 대체 포맷으로 개발됨

- 특징
  - 비손실 압축
  - 8비트(256 색상) / 24비트(약 1600만 색상) 컬러 이미지 처리
  - Alpha Channel(투명도) 지원
  - W3C 권장 포맷

#### 5-1-3. GIF(Graphics Interchange Format)

- 이미지 파일 내에 이미지 및 문자열 등의 정보 저장 가능
- 특징
  - 비손실 압축
  - 여러 장의 이미지를 한 개의 파일에 담을 수 있음
    - 움짤, 애니메이션 등 동영상 같은 이미지
  - 8비트 컬러만 지원
    - 다양한 색상을 표현하는 작업에는 적합하지 않음

#### 5-1-4. WEBP

- JPG, PNG, GIF를 모두 대체하기 위한 Google 개발 이미지 포맷
- 특징
  - 완벽한 손실/비손실 압축 지원
  - GIF 등 애니메이션 지원
  - Alpha Channel 지원
    - 손실, 비손실 모두
  - 크로스 플랫폼 이슈 존재
    - 모든 지원 브라우저에서 지원하지 않음
    - [사용 가능 브라우저](https://caniuse.com/webp)

### 5-2. 벡터(Vector)

- 수학적 정보의 형태(Shape)들이 만들어내는 결과물
- 이미지가 가지고 있는 점, 선, 면의 위치(좌표), 색상 등의 정보를 통해 화면에 렌더링
  - 수학적 정보만을 가지고 있기에 이미지 확대/축소에 따른 용량 변화가 없음
- 비트맵보다 많은 연산을 해야 하나 픽셀의 영향을 덜 받아 해상도로부터 자유로움
- svg 이미지 형식
- 일러스트 등의 툴로 편집 가능

#### 5-2-1. SVG(Scalable Vector Graphics)

- HTML/XML 마크업 언어 기반 벡터 그래픽을 표현하는 포맷
- 특징
  - 해상도의 영향에서 자유로움
    - 반응형, 크로스플랫폼 등 Device에 주로 사용
  - CSS로 Styling 가능
  - JavaScript로 Event Handling 가능
  - 코드 혹은 파일로 사용 가능
    - 동일한 개념



## 6. 특수 문자

> [HTML Entity List](https://www.freeformatter.com/html-entities.html)

| 기호 | 영어(발음)                               | 한글           |
| ---- | ---------------------------------------- | -------------- |
| `    | Grave(그레이브)                          | -              |
| ~    | Tilde(틸드)                              | 물결표시       |
| !    | Exclamation(엑스클러메이션) mark         | 느낌표         |
| @    | At(엣) sign                              | 골뱅이         |
| #    | Number(넘버) sign, Sharp(샵)             | 샵, 우물 정    |
| $    | Dollar(달러) sign                        | 달러           |
| %    | Percent(퍼센트) sign                     | 퍼센트         |
| ^    | Caret(캐럿)                              | -              |
| &    | Ampersand(엠퍼센드)                      | -              |
| *    | Asterisk(에스터리스크)                   | 별표           |
| -    | Hyphen(하이픈), Dash(대쉬)               | 마이너스       |
| _    | Underscore(언더스코어), Low dash(로대쉬) | 밑줄           |
| =    | Equals(이퀄) sign                        | 이꼬르         |
| "    | Quotation(쿼테이션) mark                 | 큰 따옴표      |
| '    | Apostrophe(아포스트로피)                 | 작은 따옴표    |
| :    | Colon(콜론)                              | 땡땡이         |
| ;    | Semicolon(세미콜론)                      | 털 달린 땡땡이 |
| ,    | Comma(콤마)                              | 쉼표           |
| .    | Period(피리어드), Dot(닷)                | 점, 마침표     |
| ?    | Question(퀘스천) mark                    | 물음표         |
| /    | Slash(슬래쉬)                            | -              |
| \|   | Vertical bar(버티컬 바)                  | -              |
| \    | Backslash(백슬래쉬)                      | -              |
| ()   | Parenthesis(퍼렌서시스)                  | (소)괄호       |
| {}   | Brace(브레이스)                          | 중괄호         |
| []   | Bracket(브래킷)                          | 대괄호         |
| <>   | Angle Bracket(앵글 브래킷)               | 꺽쇠괄호       |



## 7. Open Source License

> [OpenSource.org](https://opensource.org/licenses)

- 개발자나 특정 기업이 개발 과정에 필요한 소스 코드나 설계도를 누구나 열람할 수 있도록 공개하는 것
- 다양한 종류가 존재하며 상업적 이용에 제한이 있거나 경우에 따라 비용을 지불해야 할 수 있음
  - 따라서 오픈소스에 의존할 경우 'License'를 반드시 알아봐야 함

### 7-1. Apache License

- 아파치 소프트웨어 재단에서 자체 소프트웨어에 적용하기 위해 만든 라이선스
- 개인적/상업적 이용, 배포, 수정, 특허 신청 가능

### 7-2. MIT License

- 메사추세츠공과대학(MIT)에서 소프트웨어 학생들을 위해 개발한 라이선스
- 개인 소스에 사용하고 있다는 표시만 하면 나머지 사용에 대한 제약이 없음

### 7-3. BSD License

- BSD: Berkeley Software Distribution

- 버클리 캘리포니아 대학에서 개발한 라이선스
- MIT와 동일하게 라이선스 표시만 지켜주면 제약 없이 사용 가능

### 7-4. Beerware

- 오픈소스 개발자에게 맥주를 사줘야 하는 라이선스
  - 명분을 붙였을 뿐 사실상 무료 라이선스

