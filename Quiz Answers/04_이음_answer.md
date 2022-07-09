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

---------------------------------------------------------------

# 답안
```
Hello, my name is Shihu, and I'm undefined years old
Hello, my name is Shihu, and I'm 21 years old

```

# 작동 순서
(1) greet 함수에 name 인자 값 'Shihu' 넣어서 시작
(2) var age 변수 선언 확인 -> undefined 값 할당 -> 검토 완료
(3) 함수 처음부터 실행 -> 첫번째 console.log에 name='Shihu' & age=undefined 넣어서 실행 -> 그 결과 "Hello, my name is Shihu, and I'm undefined years old" 찍힘
(4) age='21' 참조 -> age 변수에 undefined 값 대신 21 값 할당
  (메모리는 다른 메모리 셀에 저장 & undefined 메모리셀은 쓰레기 값 garbage value 됨)
(5) 두번째 console.log에 name='Shihu' & age='21' 넣어서 실행 -> 그 결과 "Hello, my name is Shihu, and I'm 21 years old" 찍힘.
(6) greet('Shihu') 함수의 값엔 'Nice to meet you, Shihu!' 값 할당
