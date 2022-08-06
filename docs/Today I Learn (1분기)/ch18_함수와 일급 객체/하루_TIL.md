## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.06

**오늘 읽은 범위** : 18장 함수와 일급 객체

## 일급 객체

1. 무명의 리터럴을 생성할 수 있다. 즉,런타임에 생성이 가능하다.
2. 변수나 자료구조(객체, 배열) 에 저장할 수 있다.
3. 함수의 매개변수에 전달할 수 있다.
4. 함수의 반환값으로 사용할 수 있다.

- 일급 객체로서의 함수가 가지는 가장 큰 특징은 객체와 동일하게 사용할 수 있다는 것이다. 즉, 값으로 사용할 수 있는 것이다.
- 함수의 매개변수에 전달할 수 있고, 함수의 반환값으로 사용할 수도 있다.

## 함수 객체의 프로퍼티

- 함수 객체의 내부를 들여다 보면 아래와 같다.

```jsx
function square(number) {
  return number * number;
}

console.dir(square);

//결과 값
ƒ square(number)
	arguments: null
	caller: null
	length: 1
	name: "square"
	prototype: {constructor: ƒ}
	[[FunctionLocation]]: VM93:1
	[[Prototype]]: ƒ ()
	[[Scopes]]: Scopes[1]
```

- arguments, caller, length, name, prototype 프로퍼티는 모두 일반 객체에 없는 함수 객체 고유의 프로퍼티이다.

### arguments 프로퍼티

- argumets 는 객체다. 함수 호출 시 전달된 인수(argumets) 들의 정보를 담고 있는 순회 가능한 유사 배열 객체이고, 함수 내부에서 지역 변수처럼 사용된다.
- 함수 정의 시 선언한 매개변수는 함수 몸체 내부의 변수와 동일한 취급임. 즉, 함수 호출 시 함수 몸체 내에서 암묵적으로 매개변수가 선언되고 undefined 로 초기화 후 인수가 할당됨
- 선언된 매개변수의 개수 보다 인수를 적게 전달 받을 경우 전달 되지 않은 매개 변수는 undefined 값을 유지하고 개수 보다 초과 되었을 경우 무시됨(프로퍼티 값으로는 소유함)
- arguments 객체는 매개변수의 개수와 전달하는 인수의 개수를 확인하지 않기에 개수를 확정할 수 없는 가변 인자 함수를 구현할 때 유용하다.

```jsx
function sum() {
  let res = 0;

  // arguments 객체는 length 프로퍼티가 있는 유사 배열 객체이므로 for 문으로 순회할 수 있다.
  for (let i = 0; i < arguments.length; i++) {
    res += arguments[i];
  }

  return res;
}

console.log(sum());        // 0
console.log(sum(1, 2));    // 3
console.log(sum(1, 2, 3)); // 6
```

- arguments 는 유사 배열 객체다. 유사 배열 객체란 length 프로퍼티를 가진 객체로 for 문으로 순회할 수 있는 객체이다.

### caller 프로퍼티

- 비표준 프로퍼티로 중요치 않다.
- 함수 자신을 호출한 함수를 가르킨다.

### length 프로퍼티

- 함수 객체의 length 프로퍼티는 매개변수의 개수를 가르킨다.

### name 프로퍼티

- 함수 객체의 함수 이름을 나타낸다.
- 함수 이름과 식별자의 이름이 다르다는 것을 명심하자.
