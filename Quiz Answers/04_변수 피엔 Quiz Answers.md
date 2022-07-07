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

해설 및 답 입력

```js
자바스크립트 엔진은 변수,함수,클래스는 런타임 이전에 실행된다. 
그렇기에 함수 실행을 먼저 하더라도 함수 선언이 먼저 실행 되기 때문에 호출한 함수는 정상적으로 실행된다.


처음 로그가 실행될 당시 호이스팅에 의해 age의 변수가 메모리 공간을 확보한 뒤 등록되고 값이 초기화(undefined)되어있는 상태이다. 
name은 함수를 실행하며 'Shihu'값을 인수로 받았기에 name 값이 초기화 후 지역변수로 값이 할당 되었다.. 그에 따른 결과는 다음과 같다.
console.log(`Hello, my name is Shihu, and I'm undefined years old`)
그 다음 과정으로 값이 초기화 되어있던 age의 변수에 값을 할당 해 주었다. 이로 인해 변수 age의 메모리 공간 에는 21의 값이 할당 되었다.
결과 name 과 age 의 변수값이 모두 할당 되었다. 그에 따른 결과는 다음과 같다.
console.log(`Hello, my name is Shihu, and I'm 21 years old`)
이후 함수 실행 결과 값으로 `Nice to meet you, Shihu!`; 를 반환 후 해당 소스 코드는 마무리 된다.
```
