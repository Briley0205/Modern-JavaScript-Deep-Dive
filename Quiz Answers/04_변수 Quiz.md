### Quiz 

1. 다음 소스 코드의 결과를 예측하고, 그 이유를 설명하라.

```
greet('Shihu');

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21'
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};
```
> 호출된 함수는 실행될끼?
>> 왜 그렇게 생각하는가? </br>
(자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>> 왜 그렇게 생각하는가? </br>
(선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)

#### 해설 및 풀이

</br>
위 함수는 실행될 것이다. 왜냐하면, </br>

이 소스코드를 실행하기 전 단계인 평가 단계에서 
function 키워드를 발견한 JS 엔진은, 
함수 호이스팅을 발생시켜, 
파일의 맨 윗 단락으로 끌어올릴 것이기 때문이다.

```
function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21'
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};

greet('Shihu');
```
또한, function 내부에 있는 var 키워드를 보고,
변수 호이스팅을 통해 (함수 내부 차원에서)맨 위로 끌어 올린다.
때문에 최종적으로 실행 시 자바스크립트 엔진이 
보게 될 코드의 내용은 다음과 같다.
```
function greet(name) {
  var age; // undefined
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21' // 값의 재할당
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};

greet('Shihu');
```
평가 과정에서 var 키워드를 발견하면, 메모리 공간을 확보하고,</br>
식별자(age)와 메모리 주소를 연결, 실행 컨텍스트에 키(age)/ 값(undefined)의</br> 형태로 초기값을 부여하고 등록한다.

</br>
그 후, 소스코드가 한 줄씩 순서대로 실행되는 시점, 즉 런타임(runtime)</br> 단계에서 console.log(...)의 실행 및 'age'변수값의 재할당이 이루어진다.</br>
따라서 결과적으로 콘솔에 출력되는 것은 다음과 같다.

```
Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old
'Nice to meet you, Shihu!'
```