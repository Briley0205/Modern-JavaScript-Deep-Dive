# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.08.05-08.06

**오늘 읽은 범위** : <br>
18장, 함수와 일급 객체

<br>

## ✨**18장-함수와 일급 객체**✨

### ➡️일급 객체란?

-무명의 리터럴로 생성할 수 있는 것(런타임에 생성 가능)

-변수 및 자료 구조(배열, 객체 등)에 저장 가능한 것

-함수 매개변수에 전달할 수 있는 것

-함수 반환값으로 사용 가능한 것

❕즉, 자바스크립트 일급 객체이다.❕

<br>

### ➡️함수 객체의 프로퍼티

**1.`arguments` 프로퍼티** <br>
`arguments` 객체는 함수 호출시 전달된 인수들의 정보를 담고 있는 순회 가능한 유사 배열 객체이다. 함수 내부에서만 지역 변수처럼 참조할 수 있다.

```js
function plus(a, b) {
  console.log(arguments);
  return a + b;
}

console.log(plus()); //NaN
console.log(plus(1)); //NaN
console.log(plus(1, 2)); //3
console.log(plus(1, 2, 3)); //3
```

함수 호출시 함수 내부에서 암묵적으로 매개 변수가 선언됨 -> undefined로 초기화됨 -> 이후 인수가 할당됨

인수가 전달되지 않은 매개변수는 undefined로 초기화된 상태를 유지한다.

반면 매개변수 개수보다 더 많은 인수가 전달되었을 경우에는 초과된 인수는 무시된다. 버려지는 건 아니다.

<img width="380" alt="image" src="https://user-images.githubusercontent.com/106219241/183248532-8bd1b0dd-dd81-45f0-820a-b2c263891bdf.png">

arguments 객체는 인수를 프로퍼티 값으로 가지며, 프로퍼티 키는 인수 순서를 나타내는 걸 알 수 있다.

arguments 객체는 매개변수 개수를 확정할 수 없는 가변 인자 함수를 구현할 때 유용하다.

```js
function plus() {
  let number = 0;
  for (let i = 0; i < arguments.length; i++) {
    number += arguments[i];
  }
  return number;
}

console.log(plus()); // 0
console.log(plus(1, 2)); // 3
console.log(plus(1, 2, 3)); //6
```

arguments 객체는 실제 배열이 아닌 **유사 배열 객체**이다. 때문에 배열 메서드를 사용할 경우 에러가 발생하니 주의하자.

<br>

**2.`caller` 프로퍼티** <br>
ECMAScript에 포함되지 않은 비표준 프로퍼티. 함수 객체 caller 프로퍼티는 함수 자신을 호출한 함수를 가리킨다.

<br>

**3.`length` 프로퍼티** <br>
`length`프로퍼티는 함수 정의시 선언한 매개변수의 개수를 가리킨다.

```js
function newFunc(a) {
  return a;
}
console.log(newFunc.length); // 1

function newFunc(a, b) {
  return a + b;
}
console.log(newFunc.length); // 2
```

❕arguments 객체 length 프로퍼티는 인자의 개수를, 함수 객체 프로퍼티는 매개변수의 개수를 가리킨다.

<br>

**4.`name` 프로퍼티** <br>
`name`프로퍼티는 함수 이름을 나타낸다. ES5와 ES5에서는 동작을 달리하므로 주의하자. 익명 함수 표현식 경우 ES5에서 name 프로퍼티는 빈 문자열을 값으로 갖는다. 반면 ES6에서는 함수 객체를 가리키는 식별자를 값으로 가진다.<br>
<-함수 호출시 함수 이름이 아닌 함수 객체를 가리키는 식별자로 호출하는 것이다. 함수 이름과 함수 객체 가리키는 식별자는 다르다!

<br>

**5.`__proto__` 프로퍼티** <br>
모든 객체는 `[[prototype]]`이라는 내부 슬롯을 갖고 있다. 이 프로퍼티는 `[[prototype]]` 내부 슬롯이 가리키는 프로토타입 객체에 접근하기 위해 사용하는 접근자 프로퍼티이다. 직접적이 아닌 간접적으로 접근할 때 이 프로퍼티를 사용한다.

<br>

**6.`prototype` 프로퍼티** <br>
생성자 함수로 호출할 수 있는 함수 객체, constructor만이 소유하는 프로퍼티이다.

---

<br>

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
hasOwnProperty 메서드 :
인수로 전달받은 프로퍼티 키가 객체 고유의 프로퍼티 키인 경우에만 true를 반환하고 상속받은 프로토타입의 프로퍼티 키인 경우 false를 반환함
```

<br>

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
__prototype__는 모든 객체에 있는 프로퍼티인 것이고, prototype은 함수 객체만이 가진 프로퍼티라는 차이점이 있다는 것, 자바스크립트는 프로토타입 기반 객체지향 언어...
자바스크립트에서 객체가 생성될때 생성된 객체의 부모가 되는 객체의 원형을 프로토타입 객체(Prototype Object)라고 하며, 생성된 객체와 부모 객체와의 참조를 이어주는 링크를 프로토타입 링크(Prototype Link)라고 한다고 한다. 자바스크립트의 근간이 프로토타입이라는 건 알겠지만...더 공부가 필요할 것 같다. 아직은 어렵다...

```
