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
> 호출된 함수는 실행될까?
>> 실행된다.<br>
로그에 찍히는 순서는<br> 
첫번째 - Hello, my name is Shihu, and I'm undefined years old<br>
두번째 - Hello, my name is Shihu, and I'm 21 years old<br>
이며 return되는 값은<br>
'Nice to meet you, Shihu!'<br>
이다. 이것은 자바스크립트의 호이스팅 때문이다.

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>> 첫 consol.log의 age는 undefined, 그 외 이후의 변수는 값을 정확하게 불러 올 것이다. <br>
소스코드 평가 단계에서 호이스팅되어 선언문 var age는 메모리셀에 공간을 확보하고 초기화 후 "undefined"으로 재할당된 상태일 것이다.<br>
이후 런타임에 인터프리터로 한 줄씩 코드가 실행이 될 것인데, 첫번째 console.log에선 name은 정의되었지만 age = '21'가 실행되기 전이므로 참조된 age는 undefined를 나타낸다. 다음의 두번째 console.log 에선 age = '21'가 실행된 이후이므로, age가 재할당되어 '21'의 변수값을 가진 상태이다. 그래서 name과 age 모두 의도한대로의 값 Shihu와 21을 실행시키고, 마지막 문장을 return하여 함수가 실행된다.

해설 및 답 입력
```
실행결과 :
Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old
'Nice to meet you, Shihu!'
```