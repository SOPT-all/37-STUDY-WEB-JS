## Q1.

다음 코드 실행 시 일어나는 순서를 올바르게 나열하시오.

 

```jsx
const title = document.querySelector('h1');
title.textContent = 'Hello DOM';
```

1. 렌더링 엔진이 DOM 트리 내부에서 `<h1>` 요소 탐색
2. JS 엔진이 `document.querySelector` 호출
3. 렌더링 엔진이 Host Object 형태로 결과 반환
4. JS 엔진이 반환받은 객체의 `textContent` 변경
5. 렌더링 엔진이 DOM 변경사항을 반영 (Reflow → Repaint)

## Q2.

다음 중 올바른 설명을 모두 고르시오.

A. 렌더링 엔진은 HTML/CSS를 파싱해 DOM과 CSSOM을 생성한다.

B. 자바스크립트 엔진은 렌더링 엔진 내부에 포함되어 동작한다.

C. 두 엔진은 Web API를 통해 데이터를 교환한다.

D. 자바스크립트 엔진이 DOM 트리를 직접 조작한다.

## **Q3.**

브라우저의 구조를 구성 요소별로 올바르게 연결하시오.

| 구성 요소 | 역할 |
| --- | --- |
| A. 렌더링 엔진 | (a) JS 코드 실행, Web API 호출 |
| B. 자바스크립트 엔진 | (b) HTML/CSS 파싱 → DOM, CSSOM 트리 생성 |
| C. 브라우저 엔진 | (c) UI와 렌더링 엔진 사이에서 명령 조율 |

## **Q4.**

OX퀴즈 틀린 경우 올바르게 수정하시오.

1. 렌더링 엔진과 자바스크립트 엔진은 하나의 동일한 엔진 안에서 동작한다.
2. Web API는 ECMAScript 명세에 포함된 기능이다.
3. `window` 객체는 브라우저가 전역 실행 컨텍스트를 생성할 때 주입된다.
4. `document` 객체는 브라우저가 제공한 Host Object이다.