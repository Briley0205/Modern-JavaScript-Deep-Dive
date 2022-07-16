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
>
> > 왜 그렇게 생각하는가? </br>
> > (자바스크립트 엔진의 눈에는 소스 코드가 어떤 식으로 보이게 될지, 어떤 기능 때문에 왜 그렇게 보이게 될 지 서술하시오.)

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
>
> > 왜 그렇게 생각하는가? </br>
> > (선언된 변수의 3단계 라이프 사이클 (등록 => 초기화 => 할당)과 값의 할당 시기를 고려하여, 스크린 화면 너머의 과정(메모리, 엔진 등이 거치는 과정)을 설명하고, 결과를 작성하시오)

#### 해설 및 풀이

해설 및 답 입력

> 호출된 함수는 실행될까?

- 1. 실행된다. 해봤는데 된다.

> 왜 그렇게 생각하는가? </br>

- 2. 변수가 let이나 const가 아닌 var이기 때문에 호이스팅이 발생해서 된다.

> 위 함수는 어떻게 실행될까 ? 소스코드의 실행 결과는 어떨까?
> 첫번째거는 undefined, 두번째 거는 할당된 값이 나온다.

```
print Hello, my name is Shihu, and I'm undefined years old
print Hello, my name is Shihu, and I'm 21 years old
```

> > 왜 그렇게 생각하는가? </br>

- 3. 자바스크립트 엔진의 동작과정이 등록 -> 초기화 -> 할당의 순서를 거치기 때문이다.

자바스크립트 엔진은 소스코드를 한 줄씩 순차적으로 실행하기에 앞서, 먼저 소스코드의 평가(evaluation) 과정을 거치면서 소스코드 실행을 위한 준비를 한다.
엔진은 변수 선언을 포함한 모든 선언문(변수 선언문, 함수 선언문 등)을 소스코드에서 찾아내 먼저 실행한다.
소스코드 평가 과정이 끝나면, 변수 선언을 포함한 모든 선언문을 제외하고 소스코드를 한 줄씩 순차적으로 실행한다.
즉, 엔진은 변수 선언이 소스코드의 어디에 있든 상관없이 다른 코드보다 가장 먼저 실행 → 변수 선언이 어디에 위치하던 상관없이 어디서든 변수를 참조할 수 있다.

```동작과정 :
메모리 공간을 확보 -> 변수의 이름과 메모리 공간의 주소를 연결 ->
변수 이름을 실행 컨텍스트에 등록 ->
메모리 공간을 초기화 -> 런타임에 변수 값을 할당
```

- 첫 문장에서는 초기화만 되어 있고 할당이 아직 안되어서 undefined가 나오고 두번째 문장은 var 뒤에 쓰여서 변수 값을 제대로 할당받았다.

```
greet('Gather');

function greet(name) {
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  age = '21'
  var age;
  console.log(`Hello, my name is ${name}, and I'm ${age} years old`)
  return `Nice to meet you, ${name}!`;
};
```
