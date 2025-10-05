##CSS 속성 선택자(Attribute Selector)

기본 형태 : 선택자[속성=값] { ... }

- 특정 속성을 가지고, 그 값이 일치하는 요소만 선택

### 예시

- input[type="text"] → input 태그 중 type이 text인 요소만 선택
- a[target="_blank"] → a 태그 중 target이 `\_blank`인 요소만 선택

### 주요 형태별 정리

1. [속성]
   해당 속성이 존재하기만 하면 선택
   예) input[name] { color: red; }
   → name 속성을 가진 모든 input 선택

2. [속성="값"]
   → 속성의 값이 정확히 일치하는 요소 선택
   예) input[type="password"] { ... }

3. [속성~="값"]
   → 속성값이 공백으로 구분된 여러 단어 중 하나가 "값"과 일치할 때 선택
   예) div[class~="active"]
   → class="box active red" 같은 경우 매칭됨

4. [속성|="값"]
   → 속성값이 "값" 또는 "값-"으로 시작하면 선택 (주로 언어 코드에서 사용)
   예) [lang|="en"] { ... }
   → lang="en" 또는 lang="en-US" 매칭

5. [속성^="값"]
   → 속성값이 "값"으로 시작하는 요소 선택
   예) a[href^="https"] { color: green; }
   → "https://..."로 시작하는 링크만 선택

6. [속성$="값"]
   → 속성값이 "값"으로 끝나는 요소 선택
   예) a[href$=".pdf"] { color: red; }
   → .pdf 파일 링크만 선택

7. [속성*="값"]
   → 속성값 안에 "값"이 포함되어 있는 요소 선택
   예) a[href*="naver"] { color: blue; }
   → href에 "naver" 문자열이 포함된 모든 링크 선택

### 여러 속성 선택자 결합 가능

예) input[type="text"][name="id"] { ... }
→ type이 text이고 name이 id인 요소만 선택
