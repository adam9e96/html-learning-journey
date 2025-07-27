# ch06 `<img>` 태그

`<img>` 태그는 HTML 문서에 이미지를 삽입하는 데 사용되는 **빈 요소(empty element)**. <br>
닫는 태그가 없으며, 속성을 통해 이미지의 정보를 제공

## 기본 문법
```html
<img src="이미지경로" alt="대체텍스트">
```

### 속성

### 1. `src` (source) - 필수 속성
이미지 파일의 경로를 지정합니다.

```html
<img src="images/photo.jpg" alt="사진">
```

### 2. `alt` (alternative text) - 필수 속성
- 이미지를 표시할 수 없을 때 대신 보여줄 텍스트
- 스크린 리더 등 접근성 도구에서 사용
- SEO에도 중요한 역할

```html
<img src="logo.png" alt="회사 로고">
```

### 3. `width` - 선택 속성
이미지의 너비를 픽셀 단위로 지정

```html
<img src="banner.jpg" alt="배너" width="800">
```

### 4. 기타 유용한 속성

| 속성 | 설명 | 예제 |
|------|------|------|
| `height` | 이미지 높이 지정 | `height="600"` |
| `title` | 마우스 오버 시 툴팁 | `title="상세 설명"` |
| `loading` | 로딩 방식 지정 | `loading="lazy"` |
| `srcset` | 반응형 이미지 지원 | `srcset="image-2x.jpg 2x"` |

## 웹에서 지원하는 이미지 파일 형식

### 주요 형식

| 형식 | 확장자 | 특징 | 사용 용도 |
|------|--------|------|----------|
| **JPEG** | `.jpg`, `.jpeg` | 손실 압축, 작은 파일 크기 | 사진, 복잡한 이미지 |
| **PNG** | `.png` | 무손실 압축, 투명도 지원 | 로고, 아이콘, 투명 배경 |
| **GIF** | `.gif` | 애니메이션 지원, 256색 제한 | 간단한 애니메이션 |
| **WebP** | `.webp` | 우수한 압축률, 모던 브라우저 지원 | 웹 최적화 이미지 |
| **SVG** | `.svg` | 벡터 형식, 확대/축소 무제한 | 아이콘, 로고, 간단한 그래픽 |

### 예제
```html
<img src="photo.jpg" alt="JPEG 사진">
<img src="logo.png" alt="PNG 로고">
<img src="animation.gif" alt="GIF 애니메이션">
<img src="modern-image.webp" alt="WebP 이미지">
<img src="icon.svg" alt="SVG 아이콘">
```

## 📁 이미지 파일 경로

### 1. 상대 경로 (Relative Path)
현재 HTML 파일의 위치를 기준으로 하는 경로

```html
<!-- 같은 폴더 -->
<img src="image.jpg" alt="같은 폴더의 이미지">

<!-- 하위 폴더 -->
<img src="images/photo.jpg" alt="images 폴더의 사진">
<img src="assets/img/logo.png" alt="assets/img 폴더의 로고">
<img src="./img/sample.png" alt="img 폴더의 사진">
<!-- img/sample.png 와 ./img/sample.png 는 동일한 의미 -->
<!--  명확성과 일관성을 위해  img 대신 ./img 를 사용함 -->

<!-- 상위 폴더 -->
<img src="../image.jpg" alt="상위 폴더의 이미지">
<img src="../../photos/pic.jpg" alt="두 단계 상위 폴더의 사진">
```

#### 폴더 구조 예제
```
project/
├── index.html
├── image.jpg
├── images/
│   └── photo.jpg
└── pages/
    └── about.html
```

### 2. 절대 경로 (Absolute Path)

#### 웹 URL
```html
<img src="https://example.com/images/photo.jpg" alt="외부 이미지">
```

#### 루트 경로 (서버 기준)
```html
<img src="/images/logo.png" alt="서버 루트의 이미지">
```

### 경로 선택 가이드

| 상황 | 권장 경로 | 이유 |
|------|-----------|------|
| 같은 사이트 내 이미지 | 상대 경로 | 사이트 이동 시 유연함 |
| 외부 이미지 | 절대 경로 (URL) | 외부 리소스 접근 |
| 대규모 사이트 | 루트 기준 절대 경로 | 일관된 경로 관리 |