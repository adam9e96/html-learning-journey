# HTML 테이블 태그 
테이블 태그 구조

```html
<table>
    <tr>  <!-- 테이블 행 (Table Row) -->
        <td>셀 1</td>  <!-- 테이블 데이터 (Table Data) -->
        <td>셀 2</td>
    </tr>
    <tr>
        <td>셀 3</td>
        <td>셀 4</td>
    </tr>
</table>
```

## 주요 태그
- `<table>`: 테이블 전체를 감싸는 태그
- `<tr>`: 테이블의 행(row)을 정의
- `<td>`: 테이블의 셀(cell) 데이터를 정의
- `<th>`: 테이블 헤더 셀 (굵게 표시되고 중앙 정렬)

## 테이블 속성

### 기본 속성
```html
<table border="1" width="800" height="200" align="center">
    <!-- 테이블 내용 -->
</table>
```

| 속성 | 설명 | 예시 |
|------|------|------|
| `border` | 테이블 테두리 두께 | `border="1"` |
| `width` | 테이블 너비 | `width="800"` |
| `height` | 테이블 높이 | `height="200"` |
| `align` | 테이블 정렬 | `align="center"` |
| `bgcolor` | 배경색 | `bgcolor="#6699ff"` |

## 셀 속성

### td/th 속성
```html
<td width="100" height="50" align="center" valign="top" bgcolor="#ff0000">
    셀 내용
</td>
```

| 속성 | 설명 | 값 |
|------|------|-----|
| `width` | 셀 너비 | 픽셀값 또는 퍼센트 |
| `height` | 셀 높이 | 픽셀값 |
| `align` | 수평 정렬 | `left`, `center`, `right` |
| `valign` | 수직 정렬 | `top`, `middle`, `bottom` |
| `bgcolor` | 배경색 | 색상값 |

### 특징
- **같은 열의 다른 행 셀들도 width가 자동으로 맞춰짐**
- **height는 해당 행 전체에 영향을 미침**
- **같은 셀에 여러 height 값이 있으면 큰 값이 적용됨**

## 셀 병합

### 열 병합 (colspan)
```html
<tr>
    <td colspan="2">두 열을 병합한 셀</td>
    <td>일반 셀</td>
</tr>
<tr>
    <td>셀 1</td>
    <td>셀 2</td>
    <td>셀 3</td>
</tr>
```

### 행 병합 (rowspan)
```html
<tr>
    <td rowspan="2">두 행을 병합</td>
    <td>셀 1</td>
    <td>셀 2</td>
</tr>
<tr>
    <!-- rowspan으로 병합된 셀은 제거 -->
    <td>셀 3</td>
    <td>셀 4</td>
</tr>
```

### 병합 규칙
1. **colspan**: 열을 병합할 때는 병합될 td를 줄여야 함
2. **rowspan**: 행을 병합할 때는 다음 행에서 해당 위치의 td를 제거해야 함

## CSS 스타일링

### 외부/내부 CSS
```css
table {
    border: 1px solid #ff0c0c;
    width: 800px;
    height: 200px;
    border-collapse: collapse; /* 테두리 합치기 */
    margin: 0 auto; /* 중앙 정렬 */
}

th, td {
    border: 1px solid black;
    padding: 5px;
    text-align: center;
}

th {
    background-color: coral;
    font-weight: bold;
}

/* 클래스 선택자 */
.title {
    font-size: 22px;
    color: green;
}

.radius_img {
    border-radius: 20%;
}

.my_input {
    padding: 10px;
    width: 250px;
    outline: none;
    border: 1px solid green;
}
```

### 주요 CSS 속성
- `border-collapse: collapse`: 셀 테두리를 하나로 합침
- `text-align`: 수평 정렬 (left, center, right)
- `vertical-align`: 수직 정렬 (top, middle, bottom)
- `padding`: 셀 내부 여백
- `margin`: 테이블 외부 여백

## 인라인 스타일링

```html
<td style="color: #99ff00; font-size: 29px; background-color: #6699ff;">
    스타일이 적용된 셀
</td>

<a href="#" style="text-decoration: none; color: red; font-size: 30px;">
    스타일링된 링크
</a>
```

### 주요 인라인 스타일 속성
- `color`: 글자색
- `font-size`: 글자 크기
- `background-color`: 배경색
- `text-decoration`: 텍스트 장식 (none, underline 등)
- `border-radius`: 모서리 둥글게
