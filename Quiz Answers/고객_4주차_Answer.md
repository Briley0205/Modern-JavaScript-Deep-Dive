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

```

첫 번째 정답은 hello jenny이다 
그 이유는 첫번째로 sayHello함수 안에 있는 userName은 블록 레벨 스코프 때문에 함수 내부로 한정되어 있고 
두 번째 callYourName함수에서 console.log할때는 자바스크립트는 렉시컬 스코프라서 함수를 어디서 정의했는지에 따라 상위 스코프를 결정하기에
전역 변수인 처음에 있는 userName의 값을 가져와서 jenny가 출력되는 것이다. 

두 번째 정답은 둘다 5가 출력이된다.

var키워드로 선언하면 오직 함수의 블록 스코프에서만 지역변수가 된다.
따라서 함수 안에 있는 var i = 100은 지역변수여서 둘다 5가 출력된다.


세 번째 정답은 fruit === "mango" 이다
if문 안에있는 fruit는 블록 레벨 스코프가 적용되어 지역변수가 된다. 
따라서 아직 fruit는 전역 변수의 값인 mongo이기에 if문에 mongo라고 해주면 된다. 
const는 이름이 같은 변수를 두 번 선언할 수는 없다 
하지만 지역 스코프로 한정 짓는 다면  이름이 같아도 똑같은 변수 이름 선언할 수 있다. 

//따라서 아래처럼 가능하다
const fruit = "mango";

function isFruit() {
const fruit = "banana"; 
  if (true) {
    const fruit = "grape";
  }

  if (fruit === banana) {
    alert("👍");
    const fruit = "apple";
  }
}

isFruit();

```
