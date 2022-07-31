## Quiz

1.아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

```js
let userName = "jenny";

function sayHello() {
  let userName = "maria";
  callYourName();
}

function callYourName() {
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

  if (fruit === /*??*/) {
    alert("👍");
  }
}

isFruit();
```

---

#### 해설 및 풀이 (자유롭게 작성해주세요!)

1. 아래의 코드에서 sayHello() 호출시 어떤 문자열이 출력되는지 결과를 예상하고 이유를 설명하세요.

```
hello jenny
```

- 전역변수가 지역변수보다 우선되기 때문입니다.

2. 아래의 코드에서 console에 출력되는 값은 무엇인지 예상하고 이유를 설명하세요.

```
5
5
```

- 둘다 5입니다. 함수가 안에서 사용될 경우 지역변수를 우선으로 하는건 맞지만 매개변수로 받아와서 사용될 경우에만 i를 확인할 수 있기 때문입니다.

```
var i = 5;
function firstFunc() {
  var i = 100;
  secondFunc(i);
}

function secondFunc(i) {
  console.log(i);
}

firstFunc();
secondFunc();

```

- 그래서 이렇게 하면 firstFunc의 i가 사용되지 않게 됩니다.

3. 아래의 코드는 👍을 메시지 창으로 띄워야 합니다. ??에 들어갈 적절한 답안을 작성하고 그 이유를 설명하세요.

```
mango
```

그냥 mango를 입력하면 되는데 문제의 의도를 잘 모르겠습니다.
앞의 if 문이 1도 역할을 하지 않는 것 같습니다. 오 함정 질문인가요.

```
const fruit = "mango";

function isFruit() {
  if (true) {
    const fruit = "grape";
  }
  if (fruit === "mango") {
    alert("👍");
  }
}

isFruit();
```
