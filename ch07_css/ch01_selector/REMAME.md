## CSS(Cascading Style Sheets)

---

### CSS란?

**CSS**는 웹페이지의 디자인과 레이아웃을 꾸미는 데 사용되는 스타일 시트 언어.

### CSS 기본 문법

CSS는 **선택자(Selector)**, **속성(Property)**, **값(Value)**으로 구성.

`선택자 { 속성 : 값; }`

- **선택자**: 스타일을 적용할 HTML 요소를 선택.
- **속성**: 변경하고 싶은 스타일의 종류를 지정(예: `color`, `font-size`).
- **값**: 속성에 적용할 구체적인 값을 설정(예: `blue`, `16px`).

`p { color: blue; }`

위 코드는 `<p>` 태그로 작성된 모든 문단의 글자 색을 파란색으로 변경한다
만약 여러 속성을 적용하고 싶다면 세미콜론(;)으로 구분하여 추가.

`p {`
`  color: blue;`
`  font-size: 16px;`
`}`

### CSS 적용 방법

CSS를 HTML에 적용하는 방법은 크게 세 가지

#### 1. 인라인 스타일 (Inline Style)

HTML 태그 안에 **`style`** 속성을 직접 사용하여 스타일을 적용하는 방법.

```html
<h1 style="color: purple; font-size: 24px;">Hello World</h1>
```

**장점**: 하나의 요소에만 빠르게 스타일을 적용할 수 있음.
**단점**: 많은 요소에 적용하기 어렵고, HTML과 CSS 코드가 섞여서 관리가 복잡해짐.

#### 2. 내부 스타일 시트 (Internal Style Sheet)

HTML 문서의 `<head>` 태그 안에 **`<style>`** 태그를 사용하여 스타일을 적용하는 방법.

```html
<head>
  <style>
    body {
      background-color: lightgray;
    }
  </style>
</head>
<body>
  <h1>안녕하세요!</h1>
</body>
```

**장점**: 하나의 HTML 파일 안에서 전체 스타일을 관리하기 편리.
**단점**: 여러 HTML 파일에 동일한 스타일을 적용하려면 모든 파일에 동일한 코드를 복사해야 해서 비효율적

#### 3. 외부 스타일 시트 (External Style Sheet)

가장 많이 사용되는 방법으로, **별도의 `.css` 파일을 만들고 HTML에 연결**하는 방법입니다.

먼저 `style.css`라는 파일을 만들고 내용을 작성합니다.

**`style.css`**

```css
h1 {
  color: green;
}
```

그리고 HTML 문서의 `<head>` 태그에 `<link>` 태그를 사용해 이 파일을 연결합니다.

**`index.html`**

```html
<head>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1>외부 스타일 시트 예시</h1>
</body>
```

**장점**: 여러 HTML 파일이 하나의 CSS 파일을 공유할 수 있어 유지보수가 쉽고, 코드의 재사용성이 높아져요. HTML과 CSS를 분리하여 관리하기 때문에 구조가 깔끔해집니다.
**단점**: 파일을 따로 관리해야 합니다.

### 우선순위

스타일이 충돌할 경우, 어떤 규칙이 최종적으로 적용될까요? CSS는 기본적으로 **나중에 작성된 스타일**이 우선됩니다. 하지만 스타일 적용 방법마다 **우선순위**가 있어요.

**인라인 스타일 \> 내부/외부 스타일 시트**

- **인라인 스타일**이 가장 높은 우선순위를 가집니다.
- **내부 스타일 시트**와 **외부 스타일 시트**는 일반적으로 동일한 우선순위를 가지며, 둘 중 나중에 작성된 규칙이 적용돼요.

**예시:**

`index.html`

```html
<head>
  <style>
    h1 {
      color: blue;
    }
  </style>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <h1 style="color: red;">제목</h1>
</body>
```

`style.css`

```css
h1 {
  color: green;
}
```

이 경우, `h1` 태그의 색상은 **빨간색**으로 표시됩니다.
가장 높은 우선순위인 인라인 스타일이 적용되기 때문이죠.

CSS의 기초를 잘 이해하면 멋진 웹페이지를 만들 수 있으니, 이 기본 개념들을 바탕으로 더 심화된 내용을 공부해 보세요.
혹시 더 궁금한 점이 있다면 언제든지 물어보세요\!
