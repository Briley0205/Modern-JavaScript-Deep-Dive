# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.08.11

**오늘 읽은 범위** : <br>
19장, 프로토타입

<br>

## **19장 - 프로토타입**

### 오버라이딩, 프로퍼티 섀도잉

오버라이딩 : 상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의하여 사용하는 방식이다. 

```js
const Player = (function () {
  //생성자 함수
  function Player(name) {
    this.name = name;
  }
  //프로토타입 메서드
  Player.prototype.sayHello = function () {
    console.log(`Hi! my name is ${this.name}`);
  };
  //생성자 함수 반환
  return Player;
})();
const me = new Player("John");

  me.sayHello() // Hi! My name is John
//인스턴스 메서드
me.sayHello = function () {
  console.log(`Hey, my name is ${this.name}`);
};
//인스턴스 메서드가 호출됨. 프로토타입 메서드는 인스턴스 메서드에 의해 가려진다
me.sayHello();  //Hey, my name is John
```

프로토타입이 소유한 프로퍼티를 프로토타입 프로퍼티,
인스턴스가 소유한 프로퍼티를 인스턴스 프로퍼티라고 부른다. 

프로토타입 프로퍼티와 같은 이름의 프로퍼티를 인스턴스에 추가하면 프로토타입 체인을 따라 프로토타입 프로퍼티를 검색하여 프로토타입 프로퍼티를 덮어쓰는것이 아니라
인스턴스 프로퍼티로 추가한다.

이때 인스턴스 메서드 sayHello는 프로토타입 메서드 sayHello를 오버라이딩했고 프로토타입 메서드 sayHello는 가려진다.
이처럼 상속 관계에 의해 프로퍼티가 가려지는 현상을 프로퍼티 섀도잉이라한다. 


프로퍼티를 삭제하는 경우도 마찬가지다. 위 예제에서 추가한 인스턴스 메서드 sayHello를 삭제해보자.
```js
// 인스턴스 메서드를 삭제한다.
delete me.sayHello;
//인스턴스에는 sayHello 메서드가 없으므로 프로토타입 메서드가 호출된다. 
me.sayHello(); // Hi! my name is John

```
인스턴스 메서드 sayHello가 삭제된다. 
여기서 다시 삭제 시도를 해도 프로토타입의 프로퍼티를 변경 또는 삭제하는 것은 불가능 하다. 

한마디로 하위 객체를 통해 프로토타입 get 액세스는 허용되나 set 액세스는 허용되지 않는다. 

프로토타입 프로퍼티를 변경 또는 삭제하려면 하위 객체를 통해 프로토타입 체인으로 접근하는 것이 아니라 프로토타입에 직접 접근해야 한다.


```js
// 프로토타입 메서드 변경
Person.prototype.sayHello = function() {
  console.log(`Hey! My name is ${this.name}`);
};
me.sayHello(); // Hey! My name is John

// 프로토타입 메서드 삭제
delete Person.prototype.sayHello;
me.sayHello(); TypeError: me.sayHello is not a function
```

### 정적 프로퍼티/메서드

정적프로퍼티/메서드는 생성자 함수로 인스턴스를 생성하지 않아도 참조/호출할 수 있는 프로퍼티/메서드를 말한다. 

```js
//생성자 함수
function Person(name) {
  this.name = name;
}

// 프로토타입 메서드
Person.prototype.sayHello = function () {
  console.log(`Hi! My name is ${this.name}`);
};

//정적 프로퍼티
Person.staticProp = 'static prop';

//정적 메서드
Person.staticMethod = function () {
  console.log('staticMethod');
};

const me = new person('Lee');

//생성자 함수에 추가한 정적 프로퍼티/메서드는 생성자 함수로 참조/호출한다.
Person.staticMethod(); // staticMethod

//정적 프로퍼티/메서드는 생성자 함수가 생성한 인스턴스로 참조/호출할 수 없다.
// 인스턴스로 참조/호출할 수 있는 프로퍼티/메서드는 프로토타입 체인 상에 존재해야 한다.


me.staticMethod(); // TypeError: mestaticMethod is not a function
```

Person 생성자 함수는 객체이므로 자신의 프로퍼티/메서드를 소유할 수 있다.
person 생성자 함수 객체가 소유한 프로퍼티 / 메서드를 정적 프로퍼티/메서드라고 한다. 정적 프로퍼티/메서드는 생성자 함수가 생성한 인스턴스로 참조/호출할 수 없다. 

### 프로퍼티 존재 확인

#### in 연산자

in 연산자는 객체 내에 특정 프로퍼티가 존재하는지 여부를 확인한다. in 연산자의 사용법은 다음과 같다.

```js
const person = {
  name: 'Lee',
  address: 'Seoul'
};

// person 객체에 name 프로퍼티가 존재한다.
console.log('name' in person);  // true
// person 객체에 address 프로퍼티가 존재한다.
console.log('address' in person); // true
// person 객체에 age 프로퍼티가 존재하지 않는다.
console.log('age' in person); // false
```
in 연산자는 확인 대상 객체의 프로퍼티뿐만 아니라 확인 대상 객체가 상속받은 모든 프로토타입의 프로퍼티를 확인하므로 주의가 필요하다. person 객체에는 toString이라는 프로퍼티가 없지만
다음 코드의 실행 결과는 true다. 

```js
console.log('toString' in person); // true



```
이는 in 연산자가 person 객체가 속한 프로토타입 체인 상에 존재하는 모든 프로토타입에서 toString 프로퍼티를 검색했기 때문이다.
toString은 Object.prototype의 메서드다.

in 연산자 대신 ES6에서 도입된 Reflect.has 메서드를 사용할 수도 있다. Reflect.has 메서드는 in 연산자와 동일하게 동작한다. 

```js
const person = { name: 'Lee'};

console.log(Reflect.has(person, 'name'));  //true
console.log(Reflect.has(person, 'toString')); //true

```
---

정말 어렵다.  일단 조금이라도 이해되는 것부터 써봤다.  주말에 보고 또 보고 또 보고 해야겠다. 
반복만이 정답인 것 같다. 
