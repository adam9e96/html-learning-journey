# CSS 박스모델(Box Model)

모든 HTML 요소는 네모 박스로 표현되고 이 박스는 크게 4개의 영역으로 구성됨.

## 1. CSS 박스모델 구조

```
+-------------------------------+
|        Margin (바깥 여백)     |
|   +-----------------------+   |
|   |   Border (테두리)     |   |
|   |  +-----------------+  |   |
|   |  | Padding (안쪽) |  |   |
|   |  | +-----------+  |  |   |
|   |  | |  Content |  |  |   |
|   |  | +-----------+  |  |   |
|   |  +-----------------+  |   |
|   +-----------------------+   |
+-------------------------------+
```

---

### 1. Content (콘텐츠 영역)

- 텍스트, 이미지 등 실제 내용이 들어가는 영역
- 크기는 `width`, `height` 로 조절

### 2. Padding (안쪽 여백)

- 콘텐츠와 테두리(Border) 사이의 공간
- 배경색(`background`)은 패딩 영역까지 적용
- 상속되지 않음 (부모에서 자식으로 전달되지 않음)

### 3. Border (테두리)

- 콘텐츠 + 패딩을 감싸는 테두리
- 속성: `border-width`, `border-style`, `border-color`
- 테두리 두께만큼 전체 요소 크기가 커짐

### 4. Margin (바깥 여백)

- 요소와 요소 사이의 간격
- 배경색은 적용되지 않음 (투명)
- 인접한 블록 요소끼리는 margin 겹침(margin collapsing) 발생

## 2. 박스 크기 계산

기본적으로 요소의 총 너비/높이 계산은 아래와 같음.

```
총 너비 = margin-left + border-left + padding-left
        + width
        + padding-right + border-right + margin-right

총 높이 = margin-top + border-top + padding-top
        + height
        + padding-bottom + border-bottom + margin-bottom
```

---

## 3. `box-sizing` 속성

- 기본값: `content-box`

  - `width`, `height`는 Content 영역만을 의미

- `border-box`

  - `width`, `height`에 padding과 border까지 포함
  - 레이아웃 잡을 때 더 직관적이라 자주 사용됨

예시:

```css
div {
  width: 200px;
  padding: 20px;
  border: 10px solid black;
  box-sizing: content-box; /* 실제 총 너비 = 200 + 20*2 + 10*2 = 260px */
}

div.alt {
  width: 200px;
  padding: 20px;
  border: 10px solid black;
  box-sizing: border-box; /* 실제 총 너비 = 200px (고정) */
}
```

## 4. 정리

모든 요소는 **내용(Content) → 안쪽 여백(Padding) → 테두리(Border) → 바깥 여백(Margin)** 으로 쌓여 있고, `box-sizing`을 어떻게 설정하느냐에 따라 `width`, `height`의 의미가 달라짐.
