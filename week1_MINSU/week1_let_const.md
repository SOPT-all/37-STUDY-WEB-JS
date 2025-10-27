## var 키워드로 선언한 변수 문제점

### 변수 중복 선언 허용

```jsx
var x = 1;
var y = 2;

var x = 100;

var y;

console.log(x); // 100;

console.log(y); // 2
```

### 함수 레벨 스코프

var 키워드 변수는 오직 함수의 코드 블록만을 스코프로 인정

따라서 함수 외부(if, for, while 등)에서 var 키워드로 선언한 변수는 모두 전역 변수가 됨

```jsx
var x =1;

if (true) {
  var x = 10;
}

console.log(x); // 10
```

### 변수 호이스팅

var 키워드로 변수를 선언하면 변수 호이스팅에 의해 변수 선언문이 스코프의 선두로 끌어 올려진 것처럼 동작

var 키워드로 선언한 변수를 할당문 이전에 참조하면 undefined 반환

```jsx
console.log(x); // undefined

var x = 10;
```

## let 키워드

### 변수 중복 선언 금지

var 키워드는 변수를 중복 선언해도 아무 문제 없으나

let 키워드로 선언한 변수는 중복 선언하면 문법 에러가 발생

```jsx
let foo = 1;

let foo = 3; // SyntaxError
```

### 블록 레벨 스코프

var 키워드 변수는 함수 레벨 스코프를 가지나

let 키워드 변수는 블록 레벨 스코프를 가진다

즉, 모든 코드 블록(if, for, while 등)을 지역 스코프로 인정하는 블록 레벨 스코프를 따름

```jsx
let foo = 1;

{
  let foo = 2;
  let bar = 3;
}

console.log(foo);
console.log(bar); // SyntaxError: bar is not defined
```

bar 키워드는 { } 블록에서 선언된 let 변수 이므로 전역에서 참조할 수 없다

### 변수 호이스팅

let 키워드로 선언한 변수는 변수 호이스팅이 발생하지 않는 것처럼 동작한다.

let 키워드로 선언한 변수는 선언 단계와 초기화 단계가 분리되어 진행된다. 런타임 이전 자바스크립트 엔진에 의해 암묵적으로 선언 단계가 먼저 실행되지만 초기화 단계는 변수 선언문에 도달했을 대 실행됨

초기화 단계 이전에 변수에 접근하려 하면 참조 에러가 발생

let 키워드로 선언한 변수는 스코프 시작 지점부터 초기화 단계까지 변수를 참조 불가

<aside>
💡

일시적 사각지대 (TDZ - Temporal Dead Zone)

스코프의 시작 지점부터 초기화 시작 지점까지 변수를 참조할 수 없는 구간

</aside>

이렇게 let 키워드로 선언한 변수는 변수 호이스팅이 발생하지 않는 것처럼 보이나 그렇지 않음

```jsx
let foo = 1;

{
  console.log(foo); // ReferenceError: Cannot acess 'foo' before initialization
  let foo = 2;
}
```

let 키워드로 선언한 변수의 경우 호이스팅이 발생하지 않는다면 전역 변수인 foo를 참조하여 1을 출력해야 함

그러나 let 키워드로 선언한 변수도 호이스팅이 발생하기 때문에 참조 에러가 발생

let, const 포함한 모든 선언(var, let, const, function, function*, class 등)을 호이스팅 함

### 전역 객체와 let

var 키워드로 선언한 전역 변수와 전역 함수, 그로 암묵적 전역은 전역 객체 window의 프로퍼티가 됨

let 키워드로 선언한 전역 변수는 전역 객체의 프로퍼티가 아님

## const 키워드

상수를 선언하기 위해 사용하는 키워드

let의 특징과 대부분 동일

### 선언과 초기화

const 키워드로 선언한 변수는 선언과 동시에 초기화해야 함

`const foo = 1;`

`const foo;`  ← SyntexError

### 재할당 금지

const 키워드로 선언한 변수는 재할당 금지

```jsx
const foo = 1;
foo = 2 // TypeError: Assignment to constant variable
```

### 상수

const 키워드로 선언한 변수에 원시 값을 할당한 경우 변수 값을 변경할 수 없음

따라서 상태 유지와 가독성, 유지보수의 편의를 위해 적극적으로 사용해야 함

const 키워드로 선언한 상수를 통해 값의 의미를 쉽게 파악할 수 있도록 할 수 있음

상수의 경우 대문자로, 스네이크 케이스로 표현하여 사용

### const 키워드와 객체

const 키워드로 선언된 변수에 객체를 할당한 경우 값을 변경할 수 있다.

변경 가능한 값인 객체는 재할당 없이도 직접 변경이 가능하기 때문

```jsx
const person = {
  name: 'jang'
}

person.name = 'min';

console.log(person); // { name: 'min' }
```

const 키워드는 재할당을 금지할 뿐 불변을 의미하지 않음

## var vs let vs const

- ES6를 사용한다면 var 키워드는 사용하지 않는다
- 재할당이 필요한 경우 한정해 let 키워드를 사용한다. 이대의 변수의 스코프는 최대한 좁게 만든다
- 변경이 발생하지 않고 읽기 전용으로 사용하는 원시 값과 객체에는 const 키워드를사용한다
    - const 키워드는 재할당을 금지하므로 var, let 키워드보다 안전하다
