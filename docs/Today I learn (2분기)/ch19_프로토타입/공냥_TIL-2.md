# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.08.10

**오늘 읽은 범위** : <br>
19장, 프로토타입

<br>

## ✨**19장 - 프로토타입**✨

### ➡️오버라이딩, 프로퍼티 섀도잉

```js
const Player = (function () {
  //생성자 함수
  function Player(name) {
    this.name = name;
  }
  //프로토타입 메서드
  Player.prototype.sayHello = function () {
    console.log(`Hello, my name is ${this.name}`);
  };
  //생성자 함수 반환
  return Player;
})();

const me = new Player("John");

//인스턴스 메서드
me.sayHello = function () {
  console.log(`Hey, my name is ${this.name}`);
};

//인스턴스 메서드가 호출됨. 프로토타입 메서드는 인스턴스 메서드에 의해 가려진다
me.sayHello();
//Hey, my name is John
```

위처럼 프로토타입 프로퍼티와 같은 이름의 프로퍼티를 인스턴스에 추가시(`sayHello`) 체인을 따라 프로토타입 메서드를 검색하여 프로토타입 프로퍼티를 덮어쓰는 게 아니라, **인스턴스 프로퍼티로 추가한다.**

이때 인스턴스 메서드 `sayHello`는 프로토타입 메서드 `sayHello`를 **오버라이딩**했고 프로토타입 메서드 `sayHello`는 가려진다. 이처럼 상속 관계를 프로퍼티가 가려지는 현상을 **프로퍼티 섀도잉**이라 한다.

프로토타입 프로퍼티를 변경 또는 삭제하려면 하위 객체를 통해 프로토타입 체인으로 접근하는 게 아니라, 프로토타입에 직접 접근해야 한다.

```js
Player.prototype.sayHello = function () {
  console.log(`Hey, my name is ${this.name}`);
};
me.sayHello(); //Hey, my name is John

delete Player.prototype.sayHello;
me.sayHello(); ///TypeError : me.sayHello is not a function
```

<br>

### ➡️프로토타입의 교체

1️⃣ 생성자 함수에 의한 프로토타입 교체 <br>
프로토타입을 교체한 객체 리터럴에는 constructor 프로퍼티가 없다. 프로토타입을 교체시 constructor 프로퍼티와 생성자 함수 간 연결이 파괴된다. 프로토타입으로 교체한 객체 리터럴에 constructor 프로퍼티를 추가해 프로토타입 constructor 프로퍼티를 되살릴 수 있다.

2️⃣ 인스턴스에 의한 프로토타입 교체 <br>
인스턴스의 `__proto__`접근자 프로퍼티(또는 Object.setPrototypeOf 메서드)를 통해 프로토타입을 교체할 수 있다.
마찬가지로 constructor 프로퍼티가 없으므로 constructor 프로퍼티와 생성자 함수 간 연결이 파괴된다.

프로토타입 교체를 통해 객체 간 상속 관계를 동적으로 변경하는 건 꽤나 번거롭다. 때문에 프로토타입은 직접 교체하지 않는 게 좋다.

<br>

### ➡️instanceof 연산자

instanceof 연산자는 이항 연산자로서, 좌변에 객체를 가리키는 식별자, 우변에 생성자 함수를 가리키는 식별자를 피연산자로 받는다. 우변 피연산자가 함수가 아닌 경우 TypeError가 발생한다.

우변 생성자 함수 prototype에 바인딩된 객체가 좌변 객체 프로토타입 체인 상에 존재하면 true로, 그렇지 않다면 false로 평가된다.

```js
function Player(name) {
  this.name = name;
}
const me = new Player("John");
console.log(me instanceof Player); //true
console.log(me instanceof Object); //true
```

instanceof 연산자는 프로토타입의 constructor 프로퍼티가 가리키는 생성자 함수를 찾는 게 아니라, 생성자 함수의 prototype에 바인딩된 객체가 프로토타입 체인 상에 존재하는지 확인한다.

<br>

### ➡️직접 상속

1️⃣ Object.create에 의한 직접 상속<br>
Object.create 메서드는 첫 번째 매개변수에 전달한 객체의 프로토타입 체인에 속하는 객체를 생성한다. 객체를 생성하면서 직접적으로 상속을 구현하는 것이다. <br>
❕new 연산자가 없어도 객체를 생성할 수 있다. <br>
❕프로토타입을 지정하면서 객체 생성 가능하다. <br>
❕객체 리터럴에 의해 생성된 객체도 상속 받을 수 있다. <br>
<br>

2️⃣ 객체 리터럴 내부에서 `__proto__`에 의한 직접 상속 <br>
ES6에서는 객체 리터럴 내부에서 `__proto__`접근자 프로퍼티를 사용해 직접 상속을 구현할 수 있다.

<br>

### ➡️정적 프로퍼티, 메서드

정적 프로퍼티/메서드는 생성자 함수로 인스턴스를 생성하지 않아도 참조, 호출할 수 있는 프로퍼티/메서드를 말한다.

정적 프로퍼티/메서드는 생성자 함수가 생성한 인스턴스로 참조/호출할 수 없다.

### ➡️프로퍼티 존재 확인

1️⃣ in 연산자<br>
`console.log('toString' in person);`<br>
`key in object`

```
key : 프로퍼티 키를 나타내는 문자열
object : 객체로 평가되는 표현식
```

2️⃣ Object.prototype.hasOwnProperty 메서드 <br>
`console.log(person.hasOwnProperty('name'));`<br>
인수로 전달받은 프로퍼티 키가 객체 고유 프로퍼티 키인 경우에만 true를 반환하고 상속 받은 프로토타입 프로퍼티 키인 경우 false를 반환한다.

<br>

### ➡️프로퍼티 열거

1️⃣ `for...in 문` <br>
객체 모든 프로퍼티를 순회하며 열거하려면 for...in문을 사용한다.

```
for (변수 선언문 in 객체){...}
```

```js
const player = {
  name: "john",
  address: "New York",
};

for (const key in player) {
  console.log(key + ":" + player[key]);
}
```

for...in문은 객체 프로퍼티 개수만큼 순회하며 for...in 문의 변수 선언문에서 선언한 변수에 프로퍼티 키를 할당한다.

for...in문은 객체의 프로토타입 체인 상에 존재하는 모든 프로토타입 프로퍼티 중에서 프로퍼티 어트리뷰트[[Enumerable]]의 값이 true인 프로퍼티를 순회하며 열거한다.
<br>

2️⃣ `Object.keys/values/entries 메서드`<br>
객체 자신의 고유 프로퍼티만 열거하기 위해서는 for...in문을 사용하는 것보다 Object.keys/values/entries 메서드를 사용하는 걸 권장한다.

`Object.keys` : 객체 자신의 열거 가능한 프로퍼티 키를 배열로 반환.
<br>

`Object.values` : 객체 자신의 열거 가능한 프로퍼티 값을 배열로 반환.
<br>

`Object.entries` : 객체 자신의 열거 가능한 프로퍼티 키와 값의 쌍의배열을 배열에 담아 반환.

<br>
## 📝 오늘의 책갈피

➖

---

<br>

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
오버라이딩 :
상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의하여 사용하는 방식.

오버로딩 :
함수 이름은 동일하나 매개변수 타입 또는 개수가 다른 메서드를 구현하고 매개변수에 의해 메서드를 구별하여 호출하는 방식이다. 자바스크립트는 본 방식을 지원하지 않으나 arguments 객체를 사용하여 구현할 수 있다.


```

---

특히 이번 파트는 몇 번 읽는 걸로 단번에 이해가 가지 않아서, TIL 정리하는 내내도 읽은 곳을 또 읽었다. 그럼에도 아리송하다. 직접 따라 쳐가면서 결과를 확인해도 어렵구나...
