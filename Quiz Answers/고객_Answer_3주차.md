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

실행된다. 함수 선언으로 함수를 생성하면 함수 호이스팅이되어 실행이된다. 
즉 이미 런타임 이전에 함수객체와 암묵적 식별자까지 완료되어있기때문에 문제없이 잘 작동된다.

앞에서도 말했듯이 호이스팅으로 이미 함수가 세팅되어 있기 때문에 "Shihu"라는 인수가 name이라는 매개변수로 전달이되고 그 name들이  ${name}에 할당이되어 "Shihu"가 잘 출력이된다. 

그리서 첫번째 console.log 는 name은 정상표기되지만 age부분은 undefined 가 된다 
왜냐하면 var로 선언했기에 이역시 변수 호이스팅으로 런타임 이전에 undefined로 초기화가 된다. 그리고 나서 age = "21"이 할당되기 전에 age를 사용해서 초기화 값인 undefined로 출력이되고 
두 번째 console.log는 모두 정상출력이 된다. 

Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old



```
