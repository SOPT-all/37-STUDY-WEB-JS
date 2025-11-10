## 1. 다음 코드에서 var와 let을 교체했을 때의 출력과 차이를 각 키워드의 스코프 차이와 렉시컬 환경을 관련지어 설명해주세요

```js
const funcs = [];
for (var i = 0; i < 3; i++) {
  funcs.push(function() { console.log(i); });
}
funcs.forEach(fn => fn());

```

### 출력

### 이유

---

## 2. 다음 코드의 문제점을 렉시컬 환경 관점에서 설명하고 어떤 부분을 개선하면 좋을지 설명해주세요.

```js
function attachHandler(rootEl) {
  const big = new Array(1_000_000).fill({ msg: 'heavy' });

  const btn = document.createElement('button');
  btn.textContent = 'Show';
  rootEl.appendChild(btn);

  btn.addEventListener('click', function onClick() {
    console.log('sample:', big[0].msg);
  });

  // 페이지 전환 시 호출됨
  return function cleanup() {
    rootEl.innerHTML = '';
  };
}

const root = document.getElementById('root');
const cleanup = attachHandler(root);

// ...어느 시점
cleanup();

```

### 문제점

### 개선 방법

---

## 3.  다음 useState 함수의 내부 코드를 채워 주세요

다음 코드는 useState를 간단하게 구현한 예제입니다.  

hooks는 각 useState 호출의 슬롯 저장소입니다.  
hookIndex는 이번 렌더에서 몇 번째 훅을 읽는 중인지 가리키는 포인터입니다.  
mount는 루트 컴포넌트 등록과 최초 실행을 위한 함수입니다.  
rerender는 state 값의 변경이 발생하면 루트 컴포넌트를 다시 실행합니다.  

(1)부터 (4)까지의 코드를 작성해주세요.

```tsx
export const { useState, mount } = (function () {
  const hooks = [];
  let hookIndex = 0;
  let root = null;

  function useState(initialState) {
    const i = hookIndex++;
    if (hooks[i] === undefined) hooks[i] = initialState;

    const setState = (newState) => {
      const prev = /* (1) 현재 값 가져오기 */;
      const next = /* (2) newState가 함수라면 prev로 계산, 아니면 그대로 사용 */;
      /* (3) 최신 값 저장 */
      
      rerender();
    };

    return [/* (4) 현재 값 */, setState];
  }

  function mount(component) {
    root = component;
    rerender();
  }

  function rerender() {
    hookIndex = 0;
    root && root();
  }

  return { useState, mount };
})();

function App() {
  const [count, setCount] = useState(0);
  console.log('render:', count);

  if (count < 3) {
    setCount((prev) => prev + 1);
  }
}

// 초기 렌더
mount(App);
```

(1)


(2)


(3)


(4)

