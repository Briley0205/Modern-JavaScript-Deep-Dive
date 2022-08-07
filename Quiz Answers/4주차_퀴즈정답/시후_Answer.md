### Quiz

1. 아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

> 렉시컬 스코프의 판단 기준 파악하기

▶ 정답은 `Hello jenny`이다.</br>
 : callYourName() 함수는 전역에서 정의된 함수이다.</br> 평가단계에서 함수 객체를 생성한다.</br>
 이 때 생성된 함수 객체가 기억하는 상위 스코프는 전역 스코프이다.</br>

```js
let userName = "jenny";

function sayHello() {
  let userName = "maria";
  callYourName(); // 호출되었지만,
};
function callYourName() {
  // 이 지점에서 함수가 기억하고 있는 
  // 상위 스코프는 sayHello가 아니다.
  console.log(`Hello ${userName}`); // Hello jenny
};

sayHello(); // Hello jenny
```

2. 아래의 코드에서 console에 출력되는 값은 무엇인지 예상하고 이유를 설명하세요.

> 렉시컬 스코프 결정 기준 파악하기 2

```js
var i = 5;
function firstFunc() {
  var i = 100;
  secondFunc(); // 호출된다.
}

function secondFunc() {
  // 하지만 이 지점에서 해당 함수 객체가 기억하고 있는
  // 상위 스코프는 전역 스코프이기 때문에
  // i = 5를 참조한다.
  console.log(i); // 5 
}

firstFunc(); // 5
secondFunc(); // 5
```

3. 아래의 코드는 👍을 메시지 창으로 띄워야 합니다. ??에 들어갈 적절한 답안을 작성하고 그 이유를 설명하세요.

> 렉시컬 스코프 결정 기준 파악하기 3

```js
const fruit = "mango";

function isFruit() {
  if (true) {
    // const 키워드는 일반 코드블럭도 지역 스코프로 인정한다.
    const fruit = "grape";
  }
  if (fruit === "mango") {
    alert("👍");
  }
}

isFruit();
```
▶ `자식 스코프`로 내려가면서 식별자를 검색하지 않는다. 절.대.로.!</br> 
: 따라서, isFruit()지역 스코프 내의 지역 스코프 if 코드 블록에서</br> 
다음과 같은 순서로 올려보며 식별자를 검색한다.</br>
```js
if {} 조건문의 지역 스코프 => isFruit() 함수 선언문의 지역 스코프 => 전역 스코프

const fruit = "mango"; 참조
```

---
