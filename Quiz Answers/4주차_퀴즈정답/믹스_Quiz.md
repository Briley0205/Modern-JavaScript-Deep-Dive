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

#### 1번 풀이

```js
let userName = "jenny";
//전역변수, 전역스코프를 가짐

function sayHello(){
  let userName = "maria";
  //지역변수, 지역스코프를 가짐
  callYourName();
}

function callYourName(){
  console.log(`Hello ${userName}`);
}
//함수 호이스팅

sayHello();
// 결과값 : "jenny"
```
function callYourName은 함수 호이스팅으로 런타임 전 객체 생성과 식별자에 값 할당이 마무리 된 상태이다. 그렇기 때문에 function callYourName은 전역변수 userName의 jenny를 참조한다.<br>
function sayHello에서 callYourName 부르게되면 함수 호이스팅으로 이미 jenny가 참조되어있으므로, 최종적으로 sayHello 호출 시 결과 값은 jenny로 나올 것이다.

#### 2번 풀이
```js
var i = 5;
//전역 변수

function firstFunc() {
  var i = 100;
  //지역 변수
  secondFunc();
  //함수 호이스팅으로 전역 변수 var을 참조한 secondFunc 실행 - var i = 5
}

function secondFunc() {
  console.log(i);
  //지역 변수는 함수 몸체 내부에서만 유효하므로 여기선 전역 변수를 참조한다. - var i = 5
}

firstFunc();  //결과 값 - 5
secondFunc(); //결과 값 - 5
```
#### 3번 풀이
```js
const fruit = "mango";

function isFruit() {
  //첫번째 조건문
  if (true) {
    const fruit = "grape";
  }
  //두번째 조건문
  if (fruit === /*생각하는 답 - */"mango") {
    alert("👍");
  }
}

isFruit();
```
함수 isFruit 안에서 첫번째 조건문이 성립할 경우 isFruit는 지역 변수 fruit를 값 grape로 가지게 되고 두번째 조건문의 alert은 실행될 수 없다.<br>두번째 조건문이 true가 되어야 alert이 실행이 되는데, 이 경우 스코프 체인으로 인해 fruit는 상위 스코프에 위치한 전역 변수 fruit의 값 mango를 참조하게 된다. 그렇기 때문에 fruit 값이 "mango"가 되면 이 조건문은 참이 되고, alert("👍")를 실행할 수 있게 된다.

