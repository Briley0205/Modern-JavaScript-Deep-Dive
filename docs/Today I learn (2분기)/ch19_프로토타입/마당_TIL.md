## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.09

**오늘 읽은 범위** : 19장 프로토타입

## 19장 프로토타입

자바스크립트는 객체 기반의 프로그래밍 언어이며 자바스크립트를 이루고 있는 거의 "모든 것"이 객체다. 원시 타입 primitive type의 값을 제외한 나머지 값들(함수, 배열, 정규 표현식 등)은 모두 객체다.

---

## 객체지향 프로그래밍

#객체지향\_프로그래밍 은 프로그램을 명령어 또는 함수의 목록으로 보는 전통적인 명령형 프로그래밍 imperative programming 의 절차지향적 관점에서 벗어나 여러 개의 독립적 단위, 즉 #객체 object 의 집합으로 프로그램을 표현하려는 프로그래밍 패러다임을 말한다.

실체는 특징이나 성질을 나타내는 #속성 attribute/property 을 가지고 있고, 이를 통해 실체를 인식하거나 구별할 수 있다. 다양한 속성 중에서 프로그램에 필요한 속성만 간추려 내어 표현하는 것을 #추상화 abstraction 라 한다.

"이름"과 "주소"라는 속성을 갖는 person이라는 객체를 자바스크립트로 표현하면 다음과 같다.

[예제 19-01]

```jsx
// 이름과 주소 속성을 갖는 객체
const person = {
  name: "Lee",
  address: "Seoul",
};

console.log(person); // {name: "Lee", address: "Seoul"}
```

이 때 프로그래머(subject, 주체)는 이름과 주소 속성으로 표현된 객체(object)인 person을 다른 객체와 구별하여 인식할 수 있다. 이처럼 **속성을 통해 여러 개의 값을 하나의 단위로 구성한 복합적인 자료구조**를 객체라 하며, 객체지향 프로그래밍은 독립적인 객체의 집합으로 프로그램을 표현하려는 프로그래밍의 패러다임이다.

객체지향 프로그래밍은 객체의 #상태 state를 나타내는 데이터와 상태 데이터를 조작할 수 있는 #동작 behavior 을 하나의 논리적인 단위로 묶어 생각한다. 따라서 객체는 **상태 데이터와 동작을 하나의 논리적인 단위로 묶은 복합적인 자료구조**라고 할 수 있다. 이 때 객체의 상태 데이터를 #프로퍼티 property, 동작을 #메서드 method라고 한다.

---

## 상속과 프로토타입

#상속 inheritance은 객체지향 프로그래밍의 핵심 개념으로, 어떤 객체의 프로퍼티 또는 메서드를 다른 객체가 상속받아 그대로 사용할 수 있는 것을 말한다.
자바스크립트는 프로토타입을 기반으로 상속을 구현하여 불필요한 중복을 제거한다. 중복을 제거하는 방법은 기존의 코드를 적극적으로 재사용하는 것이다.

```jsx
// bad

// 생성자 함수
function Circle(radius) {
  this.radius = radius;
  this.getArea = function () {
    // Math.PI는 원주율을 나타내는 상수
    return Math.PI * this.radius ** 2;
  };
}

// 반지름이 1인 인스턴스 생성
const circle1 = new Circle(1);
// 반지름이 2인 인스턴스 생성
const circle2 = new Circle(2);

// Circle 생성자 함수는 인스턴스를 생성할 때마다 동일한 동작을 하는
// getArea 메서드를 중복 생성하고 모든 인스턴스가 중복 소유한다.
// getArea 메서드는 하나만 생성하여 모든 인스턴스가 공유해서 사용하는 것이 바람직하다.
console.log(circle.getArea === circle.getArea); // false

console.log(circle1.getArea()); // 3.141592...
console.log(circle2.getArea()); // 12.5663...
```

```jsx
// better

// 생성자 함수
function Circle(radius) {
  this.radius = radius;
}

// Circle 생성자 함수가 생성한 모든 인스턴스가 getArea 메서드를 공유해서
// 사용할 수 있도록 프로토타입에 추가한다.
// 프로토타입은 Circle 생성자 함수의 prototype 프로퍼티에 바인딩되어 있다.

Circle.prototype.getArea = function () {
  return Math.PI * this.radius ** 2;
};

// 인스턴스 생성
const circle1 = new Circle(1);
const circle2 = new Circle(2);

// Circle 생성자 함수가 생성한 모든 인스턴스는 부모 객체의 역할을 하는
// 프로토타입 Circle.prototype으로부터 getArea 메서드를 상속받는다.
// 즉, Circle 생성자 함수가 생성하는 모든 인스턴스는 하나의 getArea 메서드를 공유한다.

console.log(circle.getArea === circle.getArea); // true

console.log(circle1.getArea()); // 3.141592...
console.log(circle2.getArea()); // 12.5663...
```

---

## 프로토타입 객체

### `__proto__` 접근자 프로퍼티

모든 객체는 `__proto__` #접근자\_프로퍼티 를 통해 자신의 프로토타입, 즉 `[[Prototype]]` 내부 슬롯에 간접적으로 접근할 수 있다. 이 접근자 프로퍼티를 이용해 간접적으로 프로토타입에 접근할 수 있다. 접근자 프로퍼티를 사용하는 이유는 상호 참조에 의해 프로토타입 체인이 생성되는 것을 방지하기 위해서다. `__proto__` 접근자 프로퍼티를 코드 내에서 직접 사용하는 것은 권장하지 않는다.

> [!note] Object.prototype
> 모든 객체는 프로토타입의 계층 구조인 #프로토타입\_체인 에 묶여 있다. 자바스크립트 엔진은 객체의 프로퍼티(메서드 포함)에 접근하려고 할 때 해당 객체에 접근하려는 프로퍼티가 없다면 `__proto__` 접근자 프로퍼티가 가리키는 참조를 따라 자신의 부모 역할을 하는 프로토타입의 프로퍼티를 순차적으로 검색한다. 프로토타입 체인의 종점, 즉 프로토타입 체인의 최상위 객체는 Object.prototype이며, 이 객체의 프로퍼티와 메서드는 모든 객체에 상속된다. [[#^78a4d6]]

## 오버라이딩과 프로퍼티 섀도잉

- 프로토타입이 소유한 프로퍼티(메서드 포함)를 프로토타입 프로퍼티, 인스턴스가 소유한 프로퍼티를 인스턴스 프로퍼티라고 함.
- 상속 관계에 의해 프로퍼티가 가려지는 현상을 #프로퍼티\_섀도잉 property shadowing 이라 한다.
- 프로토타입 프로퍼티를 변경 또는 삭제하려면 하위 객체를 통해 프로토타입 체인으로 접근하는 것이 아니라 프로토타입에 직접 접근해야 한다.
  > [!abstract] 오버라이딩 overriding
  > 상위 클래스가 가지고 있는 메서드를 하위 클래스가 재정의하여 사용하는 방식

> [!abstract] 오버로딩 overloading
> 함수의 이름은 동일하지만 매개변수의 타입 또는 개수가 다른 메서드를 구현하고 매개변수에 의해 메서드를 구별하여 호출하는 방식이다. 자바스크립트는 오버로딩을 지원하지 않지만 arguments 객체를 사용하여 구현할 수는 있다.

## 프로토타입의 교체

- 프로토타입은 임의의 다른 객체로 변경할 수 있음 = 부모 객체인 프로토타입을 동적으로 변경할 수 있음
  - 이러한 특징을 활용하여 객체 간의 상속 관계를 동적으로 변경할 수 있음
  - 프로토타입은 생성자 함수 또는 인스턴스에 의해 교체할 수 있음
- ES6에서 도입된 클래스를 사용하면 간편하고 직관적으로 상속 관계를 구현할 수 있음

## instanceof 연산자

- instanceof 연산자는 이항 연산자로서 좌변에 객체를 가리키는 식별자, 우변에 생성자 함수를 가리키는 식별자를 피연산자로 받음. 우변의 피연산자가 함수가 아닌 경우 TypeError가 발생한다.
- instanceof 연산자는 **생성자 함수의 prototype에 바인딩된 객체가 프로토타입 체인 상에 존재하는지 확인한다.**

[예제19-46]

```jsx
// 생성자 함수
function Person(name) {
  this.name = name;
}

const me = new Person("Lee");

// Person.prototype이 me 객체의 프로토타입 체인 상에 존재하므로 true로 평가된다.
console.log(me instanceof Person); // true

// Object.prototype이 me 객체의 프로토타입 체인 상에 존재하므로 true로 평가된다.
console.log(me instanceof Object); // true
```

## 정적 프로퍼티/메서드

- 정적 static 프로퍼티/메서드는 생성자 함수로 인스턴스를 생성하지 않아도 참조/호출할 수 있는 프로퍼티/메서드를 말함
- 프로토타입 메서드를 호출하려면 인스턴스를 생성해야 하지만 정적 메서드는 인스턴스를 생성하지 않아도 호출할 수 있다.
- MDN상에서도 정적 프로퍼티/메서드와 프로토타입 프로퍼티/메서드를 구분하여 소개하고 있음. 표기법만으로도 이를 구별할 수 있어야함.

[예제19-56]

```jsx
// 생성자 함수
function Person(name) {
  this.name = name;
}

// 프로토타입 메서드
Person.prototype.sayHello = function () {
  console.log(`Hi! My name is ${this.name}`);
};

// 정적 프로퍼티
Person.staticProp = "static prop";

// 정적 메서드
Person.staticMethod = function () {
  console.log("staticMethod");
};

const me = new Person("Lee");

// 생성자 함수에 추가한 정적 프로퍼티/메서드는 생성자 함수로 참조/호출한다.
Person.staticMethod(); // staticMethod

// 정적 프로퍼티/메서드는 생성자 함수가 생성한 인스턴스로 참조/호출할 수 없다.
// 인스턴스로 참조/호출할 수 있는 프로퍼티/메서드는 프로토타입 체인 상에 존재해야 한다.
me.staticMethod(); // TypeError: me.staticMethod is not a function
```

## 프로퍼티 존재 확인

- in 연산자는 객체 내에 특정 프로퍼티가 존재하는지 여부를 확인한다.
- Object.prototype.hasOwnProperty 메서드를 사용해도 객체에 특정 프로퍼티가 존재하는지 확인할 수 있다.

## 프로퍼티 열거

- for...in 문 : 객체의 모든 프로퍼티를 순회하며 열거 enumeration하려면 for...in문을 사용한다.
  - `for (변수선언문 in 객체) {...}`
- Object.keys/values/entries 메서드를 사용하겨 객체 자신의 프로퍼티인지 확인하는 추가 처리가 필요함.
