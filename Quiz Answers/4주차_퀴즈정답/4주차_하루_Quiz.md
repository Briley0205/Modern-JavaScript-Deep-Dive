## Quiz

1.아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

```js
let userName = "jenny";

function sayHello(){
  let userName = "maria";
  callYourName();
}

function callYourName(){
  console.log(`Hello ${userName});
}

sayHello();
```

2.아래의 코드에서 console에 출력되는 값은 무엇인지 예상하고 이유를 설명하세요.

```js
var i = 5;
function firstFunc() {
  var i = 100;
  secondFunc();
}

function secondFunc() {
  console.log(i);
}

firstFunc();
secondFunc();
```

3.아래의 코드는 👍을 메시지 창으로 띄워야 합니다. ??에 들어갈 적절한 답안을 작성하고 그 이유를 설명하세요.

```js
const fruit = "mango";

function isFruit() {
  if (true) {
    const fruit = "grape";
  }

  if (fruit === /*??*/) {
    alert("👍");
  }
}

isFruit();
```

---

#### 해설 및 풀이 (자유롭게 작성해주세요!)
__1번__
```
let userName = "jenny";
// 1. 변수를 선언한다 이때 초기화 상태가 아니기 때문에 값 할당 이전까지는 일시적 사각지대인 상태다.
// 4. userName 에 초기화와 함께 "jenny" 라는 string 원시 값을 할당

function sayHello(){
  let userName = "maria";
  callYourName();
}
// 2. 함수 선언문으로서 sayHello 라는 식별자가 선언됨
// 6. sayHello 함수 내 지역 스코프에 userName 이 선언되고 초기화와 함께 "maria" 라는 string 원시 값을 할당
// 7. callYourName 함수 호출

function callYourName(){
  console.log(`Hello ${userName}`);
}
// 3. 함수 선언문으로서 callYourName 라는 식별자가 선언됨
// 8. Hello jenny 를 콘솔창에 출력함 (자바스크립트는 렉시컬 스코프를 따름으로 함수를 어디서 정의 했는지에 따라 스코프를 결정함 + sayHello 내 userName 은 지역 스코프에서 선언됨)

sayHello();
// 5. sayHello 함수 호출
```

</br> 

__2번__
```
var i = 5;
// 1. 변수 i 선언
// 4. i 에 5 number 값을 할당

function firstFunc() {
  var i = 100;
  // 6. i 변수에 100 number 값을 할당
  secondFunc();
  // 7. secondFunc 호출 
}
// 2. 함수 이름과 같은 식별자가 선언됨

function secondFunc() {
  console.log(i);
  // 8. 5 를 출력
  // 10. 5 를 출력 (자바스크립트는 렉시컬 스코프를 따름으로 함수를 어디서 정의 했는지에 따라 스코프를 결정함)
}
// 3. 함수 이름과 같은 식별자가 선언됨

firstFunc();
// 5. firstFunc 함수 호출
secondFunc();
// 9. secondFunc 함수 호출
```

</br>
__3번__
```
const fruit = "mango";

function isFruit() {
  if (true) {
    const fruit = "grape";
  }

  if (fruit === /*??*/) {
    alert("👍");
  }
}

isFruit();

// ?? 안에 들어갈 답은 "mango" 입니다. 
// isFruit 함수 내 첫번 째 if 문 에서 선언한 fruit 은 mango 를 할당한 fruit 과 별개의 함수 입니다. 
// === 연산자는 타입까지 같아야함으로 "mango" 입니다.
```
