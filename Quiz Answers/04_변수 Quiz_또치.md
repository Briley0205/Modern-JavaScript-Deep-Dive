### Quiz 

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

```js
여기에 해설 및 답 입력
```

호출된 함수는 실행 됩니다.

왜냐하면, 자바스크립트의 고유한 특징인 변수 호이스팅으로 인해서 function 함수가 위로 끌어 올려집니다.
그래서 소스코드를 보았을때는 호출먼저 한뒤에 함수를 작성했지만, 코드를 실행하면 런타임에 자바스크립트의 호이스팅에 의해 var age를 선언한것이 맨 위로 끌어올려져서 실행되게 됩니다.

첫번째 콘솔에서는 age가 undefined로 나오게 됩니다.
왜냐하면 runtime 이전에 호이스팅으로 인해서 변수가 선언 되어지지만, 값의 할당은 런타임에 실행되기때문에 
첫번째 콘솔에서는 age의 value가 undefined로 나오게 되며, 두번째 콘솔에서는 런타임에 순차적으로 실행되면서 age에 21 값이 들어가게 됩니다.

그래서 첫번째 콘솔에서는 'Hello, my name is Shihu, and I'm undefined years old '
두번째 콘솔에서는 'Hello, my name is Shihu, and I'm 21 years old ' 라고 나오게 됩니다.

그리고 마지막 리턴문으로 인해 'Nice to meet you, Shihu! '도 나오게 됩니다.