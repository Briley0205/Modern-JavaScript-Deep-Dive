## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.24

**오늘 읽은 범위** : 25장 클래스


# 클래스

자바스크립트는 프로토타입 기반 객체지향 언어이다. 즉, 클래스가 필요 없는 언어다. 

ES6 에서 클래스가 도입되기 이전까진 생성자 함수를 통해 객체지향의 상속을 구현 했다.

ES6 에서 부터는 클래스가 추가되었지만 많은 부분이 기존 생성자 함수와 크게 다르지 않다. 이번 챕터에서는 생성자 함수와의 차이를 중점으로 비교하고, 클래스만의 어떤 특징이 있는지 작성해보려 한다.

## 클래스 vs 생성자 함수

1. 클래스는 new 연산자 없이 호출하면 에러가 발생한다.
2. 클래스는 extends와 super 키워드를 제공한다.
3. 클래스는 const. let 키워드와 비슷하게 호이스팅이 발생하지 않는 것 처럼 동작한다.
4. 클래스 내의 모든 코드는 strict mode 가 적용된다.
5. 클래스의 [[Enumerabel]] 값은 모두 false 다.

![Untitled](https://publizm.github.io/static/21fc17dfbdef90f892d4ce7b784dda51/d0f75/classvsconstructor.jpg)

 

## 클래스 호이스팅

> 클래스 선언문으로 정의한 클래스는 런타임 이전에 평가되어 생성자 함수로서 호출할 수 있는 함수를 생성한다. 객체가 생성될 때 프로토타입도 더불어 생성된다. 단, 클래슨느 클래스 정의 이전에 참조할 수 없다.
> 

## 메서드

- constructor
- 프로토타입 메소드
- 정적 메소드

### constructor

- constructor 은 메서드로 해석되지 않고 평가 시 생성한 함수 객체 코드의 일부가 된다. 클래스 정의가 평가되면 constructor 의 기술된 동작을 하는 함수 객체가 생성된다.
- 외부에서 인스턴스 프로퍼티의 초기값을 전달하려면 아래와 같이 constructor 에 매개변수를 선언하고 인스턴스를 생성할 때 초기값을 전달한다. 초기값은 constructor 의 매개변수에게 전달된다.

```jsx
class Person {
  constructor() {
    // 고정값으로 인스턴스 초기화
    this.name = 'Lee';
    this.address = 'Seoul';
  }
}

// 인스턴스 프로퍼티가 추가된다.
const me = new Person();
console.log(me); // Person {name: "Lee", address: "Seoul"}
```

- constructor 은 한 개만 존재할 수 있으며, 생략도 가능하다. 생략 시 빈 constructor에 의해 빈 객체를 생성한다.
- constructor  내에서는 명시적 반환을 해서는 안된다.

### 프로토타입 메소드

```jsx
class Person {
  // 생성자
  constructor(name) {
    // 인스턴스 생성 및 초기화
    this.name = name;
  }

  // 프로토타입 메서드
  sayHi() {
    console.log(`Hi! My name is ${this.name}`);
  }
}

const me = new Person('Lee');
me.sayHi(); // Hi! My name is Lee
```

- 생성자 함수와 마찬가지로 클래스가 생성한 인스턴스는 프로토타입 체인의 일원이 된다.

### 정적 메소드

정적 메소드는 클래스 정의 이후 인스턴스를 생성하지 않아도 호출할 수 있다.

```jsx
class Square {
  // 정적 메서드
  static area(width, height) {
    return width * height;
  }
}

console.log(Square.area(10, 10)); // 100
```

## 상속에 의한 클래스 확장

- 클래스는 기존 클래스를 상속받아 새로운 클래스를 확장하여 정의할 수 있다.

```jsx
class Animal {
  constructor(age, weight) {
    this.age = age;
    this.weight = weight;
  }

  eat() { return 'eat'; }

  move() { return 'move'; }
}

// 상속을 통해 Animal 클래스를 확장한 Bird 클래스
class Bird extends Animal {
  fly() { return 'fly'; }
}

const bird = new Bird(1, 5);

console.log(bird); // Bird {age: 1, weight: 5}
console.log(bird instanceof Bird); // true
console.log(bird instanceof Animal); // true

console.log(bird.eat());  // eat
console.log(bird.move()); // move
console.log(bird.fly());  // fly 
```

상속을 통해 확장된 클래스를 **서브클래스** 라 부르고, 상속된 클래스를 **수퍼클래스** 라 부른다. 

- 서브클래스는 자신이 직접 인스턴스를 생성하지 않고 수퍼클래스에게 인스턴스 생성을 위임한다.
- new 연산자와 함께 호출된 함수를 가르키는 [new.target](http://new.target)은 서브클래스를 가르킨다. 따라서 인스턴스는 new.target 이 가르키는 서브클래스가 생성한 것으로 처리된다.

### **extends**

- 수퍼 클래스와 서브클래스는 인스턴스의 프로토타입 체인뿐 아니라 클래스 간의 프로토타입 체인도 생성한다. 그럼으로 프로토타입 메소드, 정적 메소드 모두 상속 가능하다.

### **super**

함수처럼 호출도 할 수 있고, 참조도할 수 있는 특수한 키워드다.

- super 를 호출하면 수퍼클래스의 constructor 이 호출된다.
- super 를 참조하면 수퍼클래스의 메서드를 호출할 수 있다.

**호출**

```jsx
// 수퍼클래스
class Base {
  constructor(a, b) { // ④
    this.a = a;
    this.b = b;
  }
}

// 서브클래스
class Derived extends Base {
  constructor(a, b, c) { // ②
    super(a, b); // ③
    this.c = c;
  }
}

const derived = new Derived(1, 2, 3); // ①
console.log(derived); // Derived {a: 1, b: 2, c: 3}
```

- 서브클래스에서 constructor 를 생략하지 않은 경우 반드시 super를 호출해야한다.
- constructor 에서 super 를 호출하기 전에는 this를 참조할 수 없다.
- super 는 반드시 constructor 에서만 호출한다.

**참조**

메서드 내에서 super 를 참조하면 수퍼클래스의 메서드 호출이 가능하다.

```jsx
// 수퍼클래스
class Base {
  constructor(name) {
    this.name = name;
  }

  sayHi() {
    return `Hi! ${this.name}`;
  }
}

// 서브클래스
class Derived extends Base {
  sayHi() {
    // super.sayHi는 수퍼클래스의 프로토타입 메서드를 가리킨다.
    return `${super.sayHi()}. how are you doing?`;
  }
}

const derived = new Derived('Lee');
console.log(derived.sayHi()); // Hi! Lee. how are you doing?
```

- 서브클래스의 sayHi 메서드 내 super.sayHi 는 수퍼 클래스의 sayHi 를 가르킨다.
- 수퍼 클래스의 sayHi가 정적 메서드 였을 경우에도 동일하게 서브 클래스의 sayHi 내 super.sayHi 는 수퍼 클래스의 sayHi 를 가르킨다.
