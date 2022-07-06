### Quiz (Mission)

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

호출된 함수는 실행될까?

==> 실행된다.

왜 그렇게 생각하는가? (자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)

==> 각 변수들이 참조 에러를 발생시키지 않기 때문이다. 참조 에러가 나지 않는 이유는 아래와 같다.


1. 소스코드의 평가 단계에서 변수 호이스팅에 의해 선언된 변수(name, age)들의 메모리 공간이 할당된다. 그리고 각 메모리 공간에는 undefined 값이 할당되어 초기화된다.
2. 소스코드의 실행 단계에서 자바스크립트 실행 컨텍스트는 greet('Shinu');를 실행한다. 이 시점에서 name과 age는 메모리 공간을 할당받았으며 undefined 초기값을 가지기 때문에 참조 에러를 발생시키지 않는다. 

위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?

Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old

왜 그렇게 생각하는가? </br>
(선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)

1. greet 함수를 위한 스택 프레임이 할당된다.
2. name 변수를 'Shihu'로 재할당한다.(새로운 메모리 공간을 할당하고 그 공간에 'Shihu' 값을 저장)
3. console에 `Hello, my name is ${name}, and I'm ${age} years old` 을 출력한다. name = 'Shihu' 이고 age = undefined 이기 때문에 console에는 Hello, my name is Shihu, and I'm undefined years old 이 출력된다.
4. age 변수를 21로 재할당한다. 
5. console에 `Hello, my name is ${name}, and I'm ${age} years old` 을 출력한다. name = 'Shihu' 이고 age = 21 이기 때문에 console에는 Hello, my name is Shihu, and I'm 21 years old 이 출력된다.
6. `Nice to meet you, ${name}!`; 를 리턴한다.
