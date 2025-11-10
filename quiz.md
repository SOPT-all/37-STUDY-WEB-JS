## Q1. 다음 코드의 출력 결과를 작성하시오.

```jsx
var x = 10;

function test() {
  console.log(x);
  var x = 20;
  console.log(x);
}

test();
console.log(x);

```

---

## Q2. 개념 OX 문제

1) `let`과 `const`도 호이스팅된다. 단, TDZ(Temporal Dead Zone) 때문에 선언 전 접근할 수 없다. ( )

2) 함수 내부에서 `var`로 선언된 변수는 전역 변수처럼 접근할 수 있다. ( )

3) `const`는 값을 변경할 수 없기 때문에, 객체나 배열을 `const`로 선언하면 내부 값도 변경할 수 없다. ( )

---

## Q3. 다음 코드에서 잘못된 부분을 찾아 수정하시오.

```jsx
const age = 200;
age = 300;
console.log(age);

```

---

## Q4. 다음 코드의 출력 결과를 작성와 이유를 간단히 설명하시오.

```jsx
function test() {
  var x = 1;
  if (true) {
    var x = 2;
  }
  console.log(x);
}
test();

```

---

## Q5. 다음 코드의 출력 결과를 작성와 이유를 간단히 설명하시오.

```jsx
var x = 10;

function outer() {
  var x = 20;

  function inner() {
    console.log(x);
  }

  inner();
}

outer();

```