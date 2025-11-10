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

## Q4. var, let, const
```js
for (var i = 0; i < 3; i++) {}
console.log(i);

for (let j = 0; j < 3; j++) {}
console.log(j);

```
첫 번째 console.log(i)는 3을 출력한다. (O/X)

두 번째 console.log(j)는 ReferenceError를 발생시킨다. (O/X)
