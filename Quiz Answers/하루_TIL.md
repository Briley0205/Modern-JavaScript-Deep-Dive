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
함수 또한 식별자이며 식별자는 선언(declaration)에 의해 자바스크립트 엔진에 식별자의 존재를 알린다.
선언된 변수는 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징인 변수 호이스팅을 가진다. 
=> 위와 같은 이유로 함수 선언이 제일 먼저 될 것이며, 함수는 실행될 것 이다.

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>> 왜 그렇게 생각하는가? </br>
>>> 1. 변수 호이스팅을 이유로 greet 이라는 함수를 선언   
>>> 2. 소스코드 작성 순서대로 greet 함수 실행. 이때 'Shihu' 파라미터 value를 줌
>>> 3. 함수가 실행되며 age 변수가 선언됨. 이때 값은 undifiend
>>> 4. 이후 소스코드 작성 순서대로 위에서 아래로 실행됨   
>>> `Hello, my name is Shihu, and I'm undifiend years old` 콘솔창에 출력
>>> 5. age에 '21' 값이 할당 됨
>>> `Hello, my name is Shihu, and I'm 21 years old` 콘솔창 출력
>>> `Nice to meet you, Shihu!` 를 return 함


#### 해설 및 풀이


```js

function greet
// 함수 선언, 이때 메모리에 공간을 확보하고 undifiend 값을 가짐

greet('Shihu');
// greet 함수 call, 'Shihu' 파라미터 value 전달, 이때 name(key) 에 'Shihu' 값이 할당됨(책에 없는 내용이라 확실치 않음..)

var age;
// age 변수 선언 메모리에 공간을 확보하고 undifiend 값을 가짐 (이후 위에서 아래로 순서대로 코드 실행)

console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
// name 프로퍼티의 value('Shihu') 는 함수 실행과 함께 전달 받았기에 name 변수에는 이미 메모리 중 임의의 공간을 확보했으며, 그 값으로 Shihu 를 할당 받음
// age 변수는 선언만 된 상태이며, 값을 할당 받지 않아 undifiend 값을 가지고 있음
// output -> Hello, my name is Shihu, and I'm undifiend years old

age = '21'
// age 값이 저장되는 메모리 위치가 변경되며 '21' 로 값이 재할당됨

console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
//age 의 값이 '21' 로 재할당 되었음으로 아래와 같이 출력됨
// output -> Hello, my name is Shihu, and I'm 21 years old

return `Nice to meet you, ${name}!`
// `Nice to meet you, Shihu!` 를 return 함

```
