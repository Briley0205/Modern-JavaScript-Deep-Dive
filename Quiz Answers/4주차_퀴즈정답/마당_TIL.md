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

### 1번

```
Hello jenny
```

변수 userName은 sayHello에서 중복 선언되고 있으나, 함수 내부에서 선언한 변수는 내부 블록에서만 유효하므로 외부 블록인 callYourName에서는 sayHello내부에서 재할당된 userName을 사용할 수 없습니다.

### 2번

```
5
```

1번과 같은 이유하고 생각합니다. 재할당이 이루어져도 함수 블록 내부에서만 유효합니다.

### 3번

```
mango
```

const로 선언한 변수는 재할당할 수 없습니다. 따라서 `const fruit = "grape";` 에서 재할당이 이루어지지 않습니다.
