# ch03 HTML 폼 요소 연습

Html의 폼(Form)에 사용되는 input 태그들을 사용하여 실제 회원가입 폼을 구현

## input 태그

input 태그는 사용자가 원하는 데이터의 값을 집접입력할 수 있는 인터페이스를 제공하는 태그

## input 태그의 속성
- `type`: input 태그에에 입력할 데이터의 종류를 정의
- `value`: input 태그에 입력된 데이터의 값을 의미. <br>사용자가 데이터를 입력할 마다 동적으로 변경됨(사용자가 input 태그에 데이터를 입력하면 해당 input 태그에서 change 이벤트가 발생하고 input 태그의 value 값이 변경됨)

## Input 태그의 다양한 타입
- `type="text"`: 일반 텍스트 입력
- `type="email"`: 이메일 입력
- `type="password"`: 비밀번호 입력(문자를 숨김)
- `type="number"`: 숫자입력
- `type="checkbox"`: 체크박스(다중 선택 가능)
- `type="radio"`: 라디오 버튼(단일 선택)
- `type="file"`: 파일 업로드
- `type="button"`: 버튼
- `type="range"`: 숫자 슬라이드

## 기타 폼 요소들
- `<textarea>`: 여러 줄 텍스트 입력
- `<select> & <option>`: 드롭다운 선택 메뉴
- `<button>`: 버튼 태그


## select 태그
드롭다운 목록 또는 셀렉트 박스라고 부르며 사용자가 옵션을 선택할 수 있는 메뉴를
제공하는 태그

```html
<form>
    <label for="user-color" style="display: block;">색상 선택</label>
    <select id="user-color" required>
        <option value="" disabled selected>좋아하는 색상 선택</option>
        <option value="red">빨강</option>
        <option value="blue">파랑</option>
        <option value="yellow">노랑</option>
        <option value="green">초록</option>
    </select>
    <button type="submit">제출</button>
</form>
```

<form>
    <label for="user-color" style="display: block;">색상 선택</label>
    <select id="user-color" required>
        <option value="" disabled selected>좋아하는 색상 선택</option>
        <option value="red">빨강</option>
        <option value="blue">파랑</option>
        <option value="yellow">노랑</option>
        <option value="green">초록</option>
    </select>
    <button type="submit">제출</button>
</form>

- `<option>` 태그는 select 태그 내의 각각의 옵션을 나타냄.



## 핵심
### 라디오 버튼은 그룹핑이 가능함
```html
<!-- name 속성이 같으면 같은 그룹으로 묶여 단일 선택만 가능 -->
<input type="radio" name="gender" value="male">남성
<input type="radio" name="gender" value="female">여성
```

### 체크박스는 다중 선택이 가능함
```html
<!-- 같은 name으로 여러 값 선택 가능 -->
<input type="checkbox" name="hobby" value="축구">축구
<input type="checkbox" name="hobby" value="야구">야구
```
### type="button" 타입은 주로 onclick 속성과 같이 쓰임
```html
<!-- 
 onclick 이벤트 헬퍼인데 click 이라는 이벤트가 발생할 때
 실행될 자바스크립트 코드를 속성값으로 넣어주면 
 click 이벤트 발생 시 해당코드가 호출됨
 -->
<input type="button" value="알림" onclick="alert('Hello !!')">
```
### type="text" vs textarea 차이
input 태그의 type="text"를 사용하면 텍스트가 input 박스의 범위를 벗어나면 
스크롤도 안생기고 옆으로만 계속 넘어가기 때문에 보기 불편해짐.<br>
textarea 태그를 사용하면 텍스트가 범위를 벗어나면 자동으로 줄바꿈이 일어나고
스크롤이 생겨서 텍스트보기가 수월함.<br>
글자수 제약이 없는 칸이나 장문의 입력이 요구되는 칸을 만들때는 input보다는
textarea 를 사용하는 것이 좋다.

```html
<p>input</p>
<input type="text">
<p>textarea</p>
<textarea></textarea>
```





### 태그 속성
- placeholder 속성: 입력 필드에 힌트 텍스트 제공
- name 속성: 서버로 데이터 전송시 식별자 역할
- value 속성: 기본값 설정 및 서버 전송 값 지정
