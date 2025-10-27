### 1. 다음 코드의 출력 결과와 이유를 작성하세요.
```
(function() {
  var secret = 'hidden';
  console.log('inside:', secret);
})();

console.log('outside:', secret);
```

출력 결과
```aiignore

```
이유:


### 2. 다음 예시 코드를 보고 출력 결과와 스코프 체인 과정에 대해 설명해주세요.
```
var x = 1;

function outer() {
  var x = 10;
  var y = 20;

  function middle() {
    var y = 100;
    console.log('middle: ', x, y);

    function inner() {
      var z = 1000;
      console.log('inner: ', x, y, z);
    }

    inner();
  }

  middle();
}

outer();

```
출력 결과
```aiignore

```

스코프 체인 과정 설명:

### var와 let 키워드로 선언한 변수의 차이점 4가지를 설명해주세요.
키워드 - 중복, 스코프, 호이스팅, 전역 객체


### 4. 선택 문제 (꼭 안해도 됨)
교재 206~207p의 즉시 실행 함수로 구현한 Counter를
class를 활용하여 구현하기

