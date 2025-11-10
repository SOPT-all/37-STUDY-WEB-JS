### Q1. 다음 코드를 바탕으로 이어지는 질문에 대답하시오.
---

```javascript
var name = 'SOHYUN';

const person = {
  name: 'JISUNG',
  printName() {
    console.log(this);
    setTimeout(function() {
        console.log("callback's this.name: ", this.name);
    }, 100);
  }
};

const anotherPerson = {
  name: 'NAEUN'
};
anotherPerson.printName = person.printName;

console.log(person.printName());
console.log(anotherPerson.printName());
```
(a) 코드의 실행 결과와 그 이유를 간략히 서술하시오.
(b)  위 코드가 문맥에 맞게 동작할 수 있도록 (= 콜백 함수가 헬퍼 함수의 역할을 제대로 수행할 수 있도록) 수정하시오.

### Q2. OX 문제
---
(1) 자바스크립트의 모든 함수는 상위 스코프를 기억하므로 일반적으로 모든 함수를 클로저라고 칭한다. (O/X)
(2) 자바스크립트 객체의 모든 프로퍼티와 메서드는 기본적으로 public하다. (O/X)

### Q3. 다음 코드를 바탕으로 이어지는 질문에 대답하시오.
---

```javascript
function createAgeTracker(ageModifier) {
  let age = 23;
    
  return function () {
    age = ageModifier(age);
    return age;
  };
}
function eatTteokguk(curAge) {
    return ++curAge;
}
function undoEatingTteokguk(curAge) {
    return --curAge;
}

const getOlder = createAgeTracker(eatTteokguk);
const getYounger = createAgeTracker(undoEatingTteokguk);

console.log(getOlder());
console.log(getOlder());
console.log(getOlder());
console.log(getOlder());
console.log(getYounger());
console.log(getYounger());
console.log(getYounger());  // 하은의 기대: 24
```
하은이는 먹은 떡국 그릇 수만큼 나이를 먹는다는 말에 속아, 코드 상에서라도 자신의 나이를 되돌리기 위해 떡국을 먹기 전으로 돌아갈 수 있는 프로그램을 만들고 싶었다.
그러나 하은의 기대와 달리  나이의 증감이 연동되지 않는 문제점이 발생하였다. 우울해하는 하은을 위해 문제점이 발생한 이유와 해결 방법을 서술하시오.

### Q4. 코드를 바탕으로 이어지는 질문에 대답하시오.
---

```javascript
function Button(props) {
    const clickHandler = () => {
        console.log(props.id);
    };
    
    return <button onClick={handleClick}>클릭</button>;
}
```
위 코드에서 `handleClick` 함수가 `props.id` 값을 정상적으로 참조할 수 있는 이유를 컴포넌트 렌더링 시점과 이벤트 발생 시점으로 나누어 상세히 설명하시오.