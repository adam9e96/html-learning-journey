# 📘 자바스크립트 자료형 (JavaScript Data Types)

## 1. 자료형 종류

자바스크립트 자료형은 크게 **원시(Primitive) 자료형**과 **참조(Reference) 자료형**으로 나뉜다.

### 원시(Primitive) 자료형

값 자체가 메모리에 직접 저장된다.

* `Number` : 정수, 실수 등 숫자형
* `String` : 문자열
* `Boolean` : true / false
* `Undefined` : 값이 정의되지 않음
* `Null` : 값이 비어있음을 의도적으로 표현
* `BigInt` : 큰 정수(2^53 이상)
* `Symbol` : 고유한 식별자

### 참조(Reference) 자료형

메모리에 **주소(참조)** 가 저장되며, 실제 값은 힙(Heap)에 존재한다.

* `Object` : 객체 `{ key: value }`
* `Array` : 배열 `[ ]`
* `Function` : 함수
* `Date`, `RegExp`, `Map`, `Set` 등 내장 객체

---

## 2. 자료형별 예시

```javascript
// Number
let age = 25;
let pi = 3.14;

// String
let name = "홍길동";
let greeting = `안녕하세요, ${name}님!`;

// Boolean
let isActive = true;
let isLoggedIn = false;

// Undefined
let x;
console.log(x); // undefined

// Null
let y = null;

// BigInt
let big = 123456789012345678901234567890n;

// Symbol
let id1 = Symbol("id");
let id2 = Symbol("id");
console.log(id1 === id2); // false

// Object
let user = { id: 1, name: "Alice" };

// Array
let numbers = [1, 2, 3, 4, 5];

// Function
function add(a, b) {
  return a + b;
}
```

---

## 3. typeof 연산자 결과

| 값            | typeof 결과              |
| ------------ | ---------------------- |
| 42           | "number"               |
| "hello"      | "string"               |
| true         | "boolean"              |
| undefined    | "undefined"            |
| null         | "object" ❗ (언어적 설계 오류) |
| 123n         | "bigint"               |
| Symbol()     | "symbol"               |
| {}           | "object"               |
| \[]          | "object"               |
| function(){} | "function"             |

---

## 4. 참고

* `null`은 **"object"** 로 나오는데, 이는 자바스크립트 초기 버그지만 호환성 문제 때문에 수정되지 않음.
* `typeof`는 기본적인 구분에 사용되며, 배열인지 확인하려면 `Array.isArray()` 사용 권장.
* 객체 내부 구조 확인은 `instanceof` 또는 `constructor` 활용 가능.