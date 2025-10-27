## Q1. 변수 호이스팅

```js
console.log(a);
var a = 10;
console.log(a);
```
위 코드의 실행 결과와 이유를 설명하라.

## Q2. 함수 호이스팅
```js
foo();
bar();

function foo() {
	console.log('foo');
}

var bar = function() {
	console.log('bar');
};
```
위 코드의 실행 결과와 이유를 설명하라.

## Q3. let, const
```js
var bar = function() {
	console.log('bar');
};
```
문제 2번의 코드에서, 해당 함수 표현식을 `let` 이나 `const` 로 선언했다면 그 실행 결과를 예측하고 이유를 설명하라.

## Q4. 클로저
```js
function outer() {
	var x=1; 
	function inner() {
		console.log(x);
	}
	x=2;
	return inner;
}

const fn = outer();
fn();
```
`inner` 는 `outer` 의 렉시컬 환경을 기억하는 클로저다. `inner` 는 `outer` 의 지역 변수 `x` 를 사용하므로, `outer` 의 렉시컬 환경을 기억하고 있다. 여기서 `inner` 가 기억하는 것은 지역변수 `x` 의 값 그 자체다. 따라서, `outer` 가 끝나면 그 바인딩은 가비지 컬렉션으로 함께 들어간다. (O/X)