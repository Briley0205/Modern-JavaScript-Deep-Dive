### Quiz (Mission)

1. 다음 소스 코드의 결과를 예측하고, 그 이유를 설명하라.

```js
greet('Shihu');

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21'
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};
```
> 호출된 함수는 실행될까?
>> 왜 그렇게 생각하는가? </br>
(자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>> 왜 그렇게 생각하는가? </br>
(선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)

#### 해설 및 풀이

자바스크립트는 각 변수, 함수, 클래스의 호이스팅이 가장 우선시 된다.
그러므로 호출을 먼저 하고 함수를 선언하더라도 상관없이 함수는 호출될 것이며
다만 호출을 가장 첫 줄에 했다고 하더라도 전역 단계에서 할당이 끝나고 난 뒤에 호출될 것으로 예상된다.

전역 함수인 greet, 변수인 name은 먼저 호이스팅 -> 초기화 -> 할당 단계를 갖게 될 것이므로

```js
function greet(name = undefined) {
  undefined
};
```

위와 같이 초기화 된 뒤 다음과 같이 값이 할당된다.

```js
function greet(name = 'Shihu') {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21'
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};
```

그리고 이제서야 첫줄의 함수 호출이 실행된다.
이때 함수 내부에서도 호이스팅 -> 초기화 -> 할당의 순서를 거친다.

```js
function greet(name = 'Shihu') {
  var age; //-- 먼저 호이스팅되어 초기화. undefined. 이후 순차실행.
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`) //-- Hello, my name is Shihu, and I'm undefined years old
  age = '21' 
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`) //-- Hello, my name is Shihu, and I'm 21 years old
  return `Nice to meet you, ${name}!`; //-- Nice to meet you, Shihu!
};
```

내부의 순차 실행으로 인해 로그를 찍은 뒤 return 값을 화면에 찍을 것이다. 맞을까?!
