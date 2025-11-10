<!-- pr 제목은 [weekn_이름] i, j, k장 퀴즈 -->
<!-- 아래 템플릿은 예시입니다! 자유로운 형식으로 변경해도 괜찮습니다! -->

## Q1.

아래 코드의 출력 결과를 쓰시오. <br/> 그 이유를 <strong>렉시컬 스코프 관점</strong>에서 설명하시오.

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

아래 코드가 <strong>호이스팅(hoisting)</strong> 된다면, 자바스크립트 엔진이 실제로 평가 단계에서 <strong>어떤 코드 구조</strong>로 인식하고 실행하는지 작성하시오.
또한 실행 컨텍스트 생성 시점(평가 단계)과 코드 실행 시점(실행 단계)에서 무슨 일이 일어나는지 간략히 설명하시오.

```js
const x = 1;
const y = 2;

function foo(a) {
  const x = 10;
  const y = 20;

  console.log(a + x + y);
}

foo(100);

console.log(x + y);
```

## Q4.

아래의 코드 실행 시 에러가 발생한다면 어떤 에러인지 쓰고, 자바스크립트 엔진이 inner 실행 시 <strong>a, b, c, d를 검색하는 과정</strong>을 실행 컨텍스트의 렉시컬 환경 구성 기준으로 단계별로 간략히 설명하시오.

```js
const a = 1;

function outer() {
  const b = 2;
  function middle() {
    const c = 3;
    function inner() {
      console.log(a, b, c, d);
    }
    inner();
  }
  middle();
}

outer();
```

## Q5.

아래의 문제를 푸시오.

(1) 자바스크립트에서 함수가 호출될 때마다 새로운 실행 컨텍스트가 생성된다. (O/X)
(2) 실행 컨텍스트 스택(Call Stack)에서 맨 위(top)에 있는 컨텍스트가 현재 실행 중인 코드의 실행 컨텍스트다. (O/X)
(3) 렉시컬 스코프는 함수가 “호출되는 시점”의 위치를 기준으로 결정된다. (O/X)

<!--## Q6. 부턴 자유롭게 추가해주세요. -->
