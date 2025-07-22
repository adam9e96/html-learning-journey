# ch03 HTML 폼 요소 연습

Html의 폼(Form)에 사용되는 태그들을 사용하여 실제 회원가입 폼을 구현(배운 것들로만)


## Input 태그의 다양한 타입
- `type="text"`: 일반 텍스트 입력
- `type="email"`: 이메일 입력
- `type="password"`: 비밀번호 입력(문자를 숨김)
- `type="number"`: 숫자입력
- `type="checkbox"`: 체크박스(다중 선택 가능)
- `type="radio"`: 라디오 버튼(단일 선택)
- `type="file"`: 파일 업로드
- `type="button"`: 버튼

## 기타 폼 요소들
- `<textarea>`: 여러 줄 텍스트 입력
- `<select> & <option>`: 드롭다운 선택 메뉴
- `<button>`: 버튼 태그


## 핵심
라디오 버튼 그룹핑
```html
<!-- name 속성이 같으면 같은 그룹으로 묶여 단일 선택만 가능 -->
<input type="radio" name="gender" value="male">남성
<input type="radio" name="gender" value="female">여성
```

체크박스 다중 선택
```html
<!-- 같은 name으로 여러 값 선택 가능 -->
<input type="checkbox" name="hobby" value="축구">축구
<input type="checkbox" name="hobby" value="야구">야구
```

드롭다운 메뉴
```html
<select name="region">
    <option>북구</option>
    <option>동구</option>
    <option>수성구</option>
</select>
```

### 태그 속성
- placeholder 속성: 입력 필드에 힌트 텍스트 제공
- name 속성: 서버로 데이터 전송시 식별자 역할
- value 속성: 기본값 설정 및 서버 전송 값 지정
