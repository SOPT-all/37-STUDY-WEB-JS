## Q1. 다음 코드를 보고, 예상 출력 결과와 이유를 작성하세요.
```html
<button id="btn">Click</button>
<script>
        const btn = document.getElementById('btn');

        btn.addEventListener('click', function() {
            console.log('A', this.id);
        });

        btn.addEventListener('click', () => {
            console.log('B', this && this.id);
        });
</script>
```

## Q2. 빈칸 채우기
* `call`은 인자를 (  )로 전달한다.
* `apply` 는 인자를 (  )로 전달한다.
* `bind` 는 `apply`와 `call` 메서드와 달리 (  )를 호출하지 않으며, (  )를 반환한다.

## Q3. 문제에 답하고, 답변에 대한 해설을 적어 주세요.
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
`inner`는 `outer`의 렉시컬 환경을 기억하는 클로저다. `inner`는 `outer` 의 지역 변수 x 를 사용하므로, `outer` 의 렉시컬 환경을 기억하고 있다. 여기서 `inner` 가 기억하는 것은 지역변수 x 의 값 그 자체다. 따라서, `outer` 가 끝나면 그 바인딩은 가비지 컬렉션으로 함께 들어간다. (O/X)

## Q4. 클로저란 무엇이고, 실무에서 어떤 이점을 가져갈 수 있는지 적어 주세요.
필수 포함 키워드: 은닉, 캡슐화