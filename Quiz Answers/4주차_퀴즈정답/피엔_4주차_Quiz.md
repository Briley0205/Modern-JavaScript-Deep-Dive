## Quiz

1.아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

```js
let userName = "jenny";

function sayHello(){
  let userName = "maria";
  callYourName();
}

function callYourName(){
  console.log(`Hello ${userName}`);
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

  if (fruit === mango) {
    alert("👍");
  }
}

isFruit();
```

---

#### 해설 및 풀이 (자유롭게 작성해주세요!)

```
1. Hello jenny가 출력된다. 자바스크립트는 함수의 정의된 위치에 따라 상위 스코프를 결정한다. callYourName 상위 스코프는 전역 스코프이므로, sayHello 함수의 변수 userName 할당은 이뤄지지 않고 callYourName함수 내의 username의 값은 전역 값 "jenny"이다.

2. 5, 5 가 출력된다. 위에 해설한것과 마찬가지로 secondFunc의 상위 스코프가 전역 변수이므로 firstFunc에서 할당한 값은 secondFunc함수에 영향을 끼치지 못한다.

3. (fruit === mango) 첫번째 if내부는 함수의 하위 스코프이다 그래서 해당 스코프에서 변수를 지정하더라도 상위 스코프로 넘어온 순간 해당 지역 변수는 사라진다. 남은건 전역 변수인 fruit = "mango" 이다. 그리하여 (fruit === mango)가 들어가야한다.

```
