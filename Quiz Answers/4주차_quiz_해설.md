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

### 해설 및 풀이 (자유롭게 작성해주세요!)

### 1번 풀이 <br>

정답은 Hello jenny 입니다.
함수 `callYourName`이 호출되는 시점이 아닌, 변수 선언 시점에 따라 스코프가 생성됩니다. 때문에 전역변수인 `userName`이 할당되면서 값인 `jenny`를 가져와 출력합니다.
<br>
❕스코프의 생성시점은 호출시점 아닌 선언시점이라는 걸 기억해둡시다.

<br>

### 2번 풀이<br>

정답은 5, 5 입니다. 상위 스코프에 있는 변수 i의 값을 참조하게 됩니다. 함수 `secondFunc`의 블록 내 코드가 실행될 때는 참조할 상위 스코프는 전역 스코프입니다. 때문에 전역 변수인 `var i = 5`를 참조합니다.

<br>

### 3번 풀이<br>

3번 문제에서는 조건문 내 지역스코프 -> isFruit 함수 내 지역 스코프 -> 전역 스코프 순으로 참조합니다. <br>
Grape는 해당 지역 내에서만 참조 가능한 변수이며, 두 번째 if문에서는 전역 변수의 값인 "Mango"를 참조합니다.<br>
❕스코프 검색은 하위에서 상위로 참조한다는 걸 기억해두면 좋을 것 같습니다.
