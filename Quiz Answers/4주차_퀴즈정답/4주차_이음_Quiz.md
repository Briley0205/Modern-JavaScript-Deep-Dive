[이음 4주차 퀴즈 정답]

## Quiz

1.아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

```js
let userName = "jenny";

function sayHello(){
  let userName = "maria";
  callYourName();
}

function callYourName(){
  console.log(`Hello ${userName}`)
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

```

1. Hello jenny
해설: callYourName과 동격의 스코프가 userName jenny이므로 jenny가 출력

2. 5 5
해설: 마찬가지로 secondFunc이 정의된 스코프가 전역 스코프이므로 var 1=5만 출력 (자바스크립트는 정의된 기준으로 스코프 결정)

3. mango
if(true) 스코프 밖이므로 fruit= mango로 정의되어 있음

```
