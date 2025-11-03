<!-- pr 제목은 [weekn_이름] i, j, k장 퀴즈 -->
<!-- 아래 템플릿은 예시입니다! 자유로운 형식으로 변경해도 괜찮습니다! -->

## Q1.

아래 코드의 출력 결과를 쓰시오. 그 이유를 <strong>렉시컬 스코프 관점</strong>에서 설명하시오.

```js
const x = 10;

function outer() {
  const x = 20;
  function inner() {
    console.log(x);
  }
  return inner;
}

const fn = outer();
fn();
```

## Q2.

아래 코드의 실행 결과를 순서대로 쓰고, 코드 실행 중 <strong>실행 컨텍스트 스택(Call Stack)</strong>의 변화 과정을 단계별로 설명하시오.

```js
var x = 1;

function first() {
  console.log("first start");
  second();
  console.log("first end");
}

function second() {
  console.log("second");
}

first();
```

## Q3.

## Q4.

## Q5.

<!--## Q6. 부턴 자유롭게 추가해주세요. -->
