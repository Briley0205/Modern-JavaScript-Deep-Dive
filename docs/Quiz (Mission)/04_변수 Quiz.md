### Quiz (Mission)

1. 다음 소스 코드의 결과를 예측하고, 그 이유를 설명하라.

```js
greet('Shihu');

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  age = '21';
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

해설 및 답 입력

```
호출된 함수는 실행될까? : Yes
왜 그렇게 생각하는가?
> 인터프리터가 선언문들을 모두 끌어올려서 해당 함수 유효 스코프 최상단에 선언하기 때문이다. 이를 호이스팅이라고한다.

```

만약 위의 코드 이름이 **greeting.js**이라 가정하였을 때

`node greeting.js` 실행시 즉시실행 함수로 선언되어 아래와 같은 형태가 될것이다.

```js
(() => {
  greet('Shihu');

  function greet(name) {
    console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
    age = '21';
    var age;
    console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
    return `Nice to meet you, ${name}!`;
  }
})();
```

즉시실행함수의 유효범위는 `{ }` 내부이며 <br/>
함수의 최상단에 선언문인 `function greet() { ... }` 이 올라오게 되어서 실행컨텍스트에 등록된다.

실행컨텍스트에 등록이 끝난후 함수의 최상단부터 한줄한줄 읽어내며 실행하게되므로 실행된다.

물론 전체함수 내부의 greet 함수안에서도 호이스팅이 발생하게 된다.

한줄한줄봐보자

```ts
function greet(name) {
  // console.log(~~~) 함수실행
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  // age 변수 초기화
  age = '21';
  // age 변수 선언
  var age;
  // console.log(~~~) 함수실행
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  // 함수종료시점
  return `Nice to meet you, ${name}!`;
}
```

`console.log`부분은 제외하고 봐보면<br>

```
3단계로 나뉜다
- 변수 초기화
- 변수 선언
- 함수 종료

호이스팅 과정을 걸치게되게된다
> 선언문을 만나면 메모리에 공간을 확보한후 undefined를 할당하여 초기화 한후  함수 유효범위 가장 위로올린다.
> 한줄 한줄 소스코드를 읽게되어서 실행시킨다.
```

결국 재 배치될 함수의 형태는 아래와 같다

```ts
function greet(name) {
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  age = '21';
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`);
  return `Nice to meet you, ${name}!`;
}
```

```
그러므로 정답은

Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old

이렇게 되는것이 맞다
```
