### Quiz (Mission)

1. 다음 소스 코드의 결과를 예측하고, 그 이유를 설명하라.

```js
greet("Shihu");

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  age = "21";
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  return `Nice to meet you, ${name}!`;
}
```

> 호출된 함수는 실행될까?
>
> > 왜 그렇게 생각하는가? </br>
> > (자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>
> > 왜 그렇게 생각하는가? </br>
> > (선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)

#### 해설 및 풀이

해설 및 답 입력 <br>
(1)호출된 함수는 실행된다. 함수 선언문 function greet는 호이스팅으로 먼저 함수가 선언이 된 후 함수 호출 및 실행으로 이어진다.

<br>

(2)자바스크립트 엔진은 코드 실행 전 실행 컨텍스트를 위한 과정을 걸친다. 실행 컨텍스트를 위한 과정에서 선언은 스코프에 등록한다. 여기에서 선언은 코드 실행보다 먼저 메모리에 저장이 된다. <br>

1. greet 함수 선언, var age 선언(+초기화)이 호이스팅으로 먼저 이루어진다.
2. greet 함수는 name에 Shihu를 받아온 반면, 변수 age는 초기화까지만 된 상태이므로 첫번째 console.log에서는 undefined 값을 갖고 있다.
3. 그 다음으로 age = '21'로 값 재할당이 이루어진다.
   두 번째 console.log에서는 Shihu와 재할당 된 값인 '21'을 갖고 출력하게 된다.
   이후 Shihu라는 값과 함께 리턴한다.

```js
greet("Shihu");

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  //function greet 함수 선언은 호이스팅으로 끌어올려진다. 함수 선언 후 호출 및 실행으로 'Shihu'라는 인자를 받게 되며 ${name}에 전달, 'Shihu'를 보여준다.
  // age는 이때 선언과 초기화만 일어난 상태다. undefined를 보여준다.
  //때문에 console은 'Shihu'와 undefined를 보여준다.

  age = "21";
  // 변수 age (undefined) 에 '21'을 재할당한다.
  var age;
  // 코드 실행에 앞서 호이스팅으로 선언이 메모리에 저장이 된다. var 키워드는 선언 및 초기화 동시에 이루어지므로, undefined로 초기화된 상태.
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  return `Nice to meet you, ${name}!`;
}
//위 console.log에서는 age 재할당('21')도 이루어진 상태이므로, 'Shihu'와 '21'을 보여준다. 그 다음으로 Nice to meet you, 'Shihu'를 리턴한다.

//Hello, my name is Shihu, and I'm undefined years old
//Hello, my name is Shihu, and I'm 21 years old
//Nice to meet you, Shihu!
```
