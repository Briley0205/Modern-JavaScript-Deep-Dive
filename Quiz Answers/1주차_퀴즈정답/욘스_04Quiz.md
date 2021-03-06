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

해설 및 답 입력

```js
Q. 호출된 함수는 실행될까?
A. 실행 될 것 같습니다!

Q. 왜 그렇게 생각하는가?
A. `var age` 선언문은 런타임 이전 단계에서 먼저 실행됐기 때문에 에러가 발생하지 않습니다.

Q. 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
A. 처음엔 `Hello, my name is Shihu, and I'm undefined years old` 라고 출력 되고,
두번째는 `Hello, my name is Shihu, and I'm 21 years old` 라고 출력됩니다.

Q. 왜 그렇게 생각하는가?
A. 자바스크립트 엔진은 소스코드를 실행하기 전, 소스코드 실행을 위한 준비단계인 평가과정을 거칩니다. 이때 자바스크립트 엔진은 변수 선언을 포함한 모든 선언문을 소스코드에서 찾아내 먼저 실행합니다. 이 때 var age로 선언한 변수가 실행되고, 선언과 동시에 초기화를 거치며 undefined 값을 갖습니다. undefined라는 값을 갖기 때문에, 사실상 초기화와 동시에 값을 할당한다고 볼 수 있습니다.
두번째 출력문에서 나이가 출력되는 이유는 런타임에 값의 재할당이 실행되기 때문입니다. age엔 이미 undefined라는 값이 할당되어 있기 때문에 할당이 아니라 재할당입니다. 메모리상으로는 이전에 undefined가 저장되어 있던 메모리 공간이 아닌, 새로운 메모리 공간을 확보해 21이라는 숫자를 저장하게 됩니다.

```
