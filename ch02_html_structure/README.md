# ch02 - HTML 기본
HTML 문서는 `.html` 확장자를 가지며, 웹 페이지의 구조와 내용을 기술하는 마크업 언어.


## HTML 기본 뼈대
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Hello World</title>
  </head>
  <body>
    <p>Hello World</p>
  </body>
</html>
```
설명
| 구성                | 설명                     |
| ----------------- | ---------------------- |
| `<!DOCTYPE html>` | HTML5 문서임을 선언          |
| `<html>`          | 전체 HTML 문서의 루트 요소      |
| `<head>`          | 문서 정보 (메타데이터, 제목 등) 포함 |
| `<body>`          | 사용자에게 보여지는 실제 콘텐츠 영역   |

### `<!DOCTYPE html>`

* 이 문서는 HTML5 문법을 사용한다는 선언.
* 반드시 문서 최상단에 위치.

### `<html> ~ </html>`

* HTML 문서의 루트(root) 요소.
* `<head>`와 `<body>`를 포함하는 최상위 태그.

### `<head> ~ </head>`

* 브라우저에 직접 표시되지 않는 문서 정보(metadata)를 담는 영역.
* 주로 `<meta>`, `<title>`, `<link>`, `<style>`, `<script>` 등이 위치한다.

#### `<meta>` 태그

* 문서의 문자 인코딩이나 기타 정보를 담는다.
* 예: `<meta charset="UTF-8">`은 한글과 같은 유니코드 문자가 제대로 표시되게 함.

#### `<title>` 태그

* 브라우저 탭에 표시될 제목.
* 검색 엔진 결과에 노출되는 제목으로도 사용됨.
* 예: `<title>나의 첫 웹페이지</title>`

### `<body> ~ </body>`

* 사용자에게 보이는 실제 웹 페이지의 콘텐츠를 담는 영역.
* 예: 텍스트, 이미지, 버튼, 폼 등.

---
## 태그 구조와 규칙
1. 태그는 시작태그 + 종료태그가 존재 <br>
예: `<p>문장</p>`, `<div>내용</div>`
2. 빈 태그(Self-closing tag)
종료태그 없이 사용하는 단톡 태그<br>
예: `<br>`, `<img>`, `<input>`

### 주의
- 빈 태그는 들여쓰기를 하지 않아도 된다.
- 시작/종료 태그는 들여쓰기를 해서 부모-자식 구조를 형성해야한다.

## 태그 속성(attribute)
태그에는 속성이 존재함<br>

태그 속성은 태그에 추가 정보를 부여하거나 동작을 제어함
```html
<태그이름 속성명="값">내용</태그이름>

<!-- 빈 태그의 경우 -->
<태그이름 속성명="값" />
```

```html
<input type="text" placeholder="이름을 입력하세요">

<!-- type 속성, placeholder 속성이 추가됨 -->
<!-- type는 입력 필드 종류를 결정하고, placeholder은 힌트 텍스트정보를 추가함 -->
```

---
## 개발 기초 개념
### 문자열 표현(`"`, `'`) 차이점
| 구분   | 설명                                     |
| ---- | -------------------------------------- |
| `""` | 문자열 (한 문자 이상 가능) 예: `"hello"`, `"abc"` |
| `''` | 문자 (1바이트만 가능, 1글자) 예: `'a'`, `'1'`     |

- 이 구분은 C언어나 저수준 프로그래밍에선 특히 중요함
- HTML에선 둘 다 문자열을 감싸는 데 사용 가능하지만 주로 `""` 사용함
- 태그 속성의 값도 `""` 사용함

## 들여쓰기와 구조
- HTML에서는 들여쓰기를 통해 부모-자식 관계를 시각적으로 표현함
- 유지보수와 가독성을 위해 들여쓰기는 반드시 지켜야함.
- 중첩 구조가 있는 경우(`<div>`,`<ul>`,`<section>`)는 특히 들여쓰기가 중요함

---

## 핵심
- HTML 작성시 기본 뼈대구조를 만든 뒤 내용을 채워나간다.
- 들여쓰기는 필수는 아니지만, 포함관계를 명확히 하여 가독성을 높이는데 중요하다.
- `<head>`는 보이지 않는 정보(문서 설정), `<body>`는 사용자가 볼 수 있는 내용이 포함된다.
- 태그는 중첩이 가능하며, 문서 구조를 논리적으로 표현한다.