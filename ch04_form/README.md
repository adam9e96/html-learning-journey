# ch04 a태그, img 태그, HTML 공백 처리

## a 태그 (Anchor Tag)

웹 페이지에서 다른 페이지, 문서, 외부 사이트 등으로 **하이퍼링크**를 연결할 때 사용.

  ```html
  <a href="링크주소">링크 텍스트</a>
  ```
* **속성**

  * `href`: 링크의 목적지를 지정.
  * `target`: 링크 클릭 시 열릴 위치를 지정.

    * `_self` (기본값): 현재 창에서 열림.
    * `_blank`: \*\*새 창(또는 새 탭)\*\*에서 열림.

### 예시

```html
<a href="https://www.google.com/">Google</a>
<a href="https://www.naver.com/" target="_blank">네이버 새창</a>
<a href="2_temp.html" target="_blank">다른 HTML 문서</a>
<a href="../ch03_input_types/02_회원가입.html" target="_blank">다른 폴더의 문서</a>
```

---

## img 태그 (Image Tag)

웹 페이지에 이미지를 삽입할 때 사용.

  ```html
  <img src="이미지경로" width="너비(px)">
  ```

### 이미지에 링크 걸기

이미지 자체를 클릭하면 링크로 연결되게 하기 위해 `<a>` 태그 안에 `<img>`를 넣음.

```html
<a href="https://www.google.com" target="_blank">
  <img src="./img/sample.webp" width="400">
</a>
```

---

## HTML에서 공백 넣는 방법

HTML에서는 연속된 공백이 하나만 인식되므로, **여러 칸의 공백**을 표현하려면 특수문자를 사용해야 함.

| 코드       | 의미                   |
| -------- | -------------------- |
| `&nbsp;` | 일반 스페이스 (1칸)         |
| `&ensp;` | 약간 더 넓은 스페이스 (2칸 정도) |
| `&emsp;` | 더 넓은 스페이스 (4칸 정도)    |

### 예시

```html
<a href="#">네&nbsp;&nbsp;&nbsp;이버</a>
<a href="#">문서&ensp;&ensp;&ensp;&ensp;보기</a>
```

---

## 정리

* `a` 태그는 하이퍼링크를 만들고 `target="_blank"`를 사용하면 새창에서 열림.
* `img` 태그는 이미지를 삽입하며 `src`로 경로 지정.
* 여러 칸 공백은 `&nbsp;`, `&ensp;`, `&emsp;` 등을 사용하여 구현.
