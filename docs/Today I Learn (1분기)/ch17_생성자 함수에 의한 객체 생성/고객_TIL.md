## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.05

**오늘 읽은 범위** : 17장 생성자 함수에 의한 객체 생성

## 생성자 함수에 의한 객체 생성 📑
---
#### Object 생성자 함수 

자바스크립트는 Object 생성자 함수 이외에도 String, Number. boolean, Function , Array, Date, RegExp, Promise등의 빌트인 생성자 함수를 제공한다.

```js
// 아래와 같이 만들 수 있다. 
const strObj = new String('Lee');

const numObj = new Number(123);

const boolObj = new Boolean(true);
```

하지만 객체 리터럴을 사용하는 것이 더 간편하기에  특별한 이유가 없다면 굳이 사용할 이유가 없다. 

---

#### 생성자 함수

객체 리터럴로 동일한 프로퍼티를 갖는 객체를 여러 개 생성해야하는 경우 매번 같은 프로퍼티를 기술해야하기 때문에 비효율적이다. 
이때 사용가능한 것이 생성자 함수이다. 



생성자 함수에 의한 객체 생성 방식은 마치 인스턴스를 생성하기 위해 클래스처럼 생성자 함수를 사용하여 프로퍼티 구조가 동일한 객체 여러 개를 간편하게 생성할 수 있다. 
예를 들어보자
```js
//생성자 함수
function Circle(radius){
  this.radius = radius;
  this.getDiameter = function(){
    return 2 * this.radius;
   };
 }
 
 // 인스턴스의 생성

  const circle1 = new Circle(5); 
  const circle2 = new Circle(10);
  
  console.log(circle1.getDiameter()); // 10
  console.log(circle2.getDiameter()); // 20
```

> this는 객체 자신의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수다. 
> this가 가리키는 값, 즉 this 바인딩은 함수 호출 방식에 따라 동적으로 결정된다.

| 함수 호출 방식  | this가 가리키는 값(this 바인딩) | 
|----|-------------|
| 일반 함수로서 호출 | 전역 객체 | 
| 메서드로서 호출 | 메서드를 호출한 객체(마침표 앞의 객체) | 
| 생성자 함수로서 호출 | 생성자 함수가 (미래에) 생성할 인스턴스 | 


생성자 함수는 이름 그대로 인스턴스를 생성하는 함수다 
일반 함수와 동일한 방법으로 생성자 함수를 정의하고 new 연산자와 함께 호출하면 해당 함수는 생성자 함수로 동작한다 
만약 new연산자와 함께 생성자 함수를 호출하지 않으면 생성자 함수가 아니라 일반 함수로 동작한다. 

```js
// new 연산자와 함께 호출하지 않았기 때문에 일반 함수로서 호출된다.
const circle3 = circle(15);

// 일반 함수로서 호출된  Circle은 반환문이 없으므로 암묵적으로 undefined를 반환한다. 
console.log(circle3) undefined

//일반 함수로서 호출된 Circle 내의 this는 전역 객체를 가리킨다.
console.log(radius); // 15
```
만약 new연산자와 함께 생성자 함수를 호출하지 않으면 생성자 함수가 아니라 일반 함수로 동작한다.

##### 생성자 함수의 인스턴스 생성과정

그렇다면 어떠한 원리로 이렇게 사용이 가능한걸까?


생성자 함수의 역할은 프로퍼티 구조가 동일한 인스턴스를 생성하기 위한 템플릿(클래스)으로서 동작하여 인스턴스를 생성하는 것과 
생성된 인스턴스를 초기화(인스턴스 프로퍼티 추가 및 초기값 할당)하는 것이다

생성자 함수가 인스턴스를 생성하는 것은 필수이고
생성된 인스턴스를 초기화하는 것은 옵션이다. 

순서는 아래와 같다

1. 인스턴스 생성과 this 바인딩
2. 인스턴스 초기화
3. 인스턴스 반환


예제를 보면서 적용해보자 

```js
function Circle(radius){
// 1. 암묵적으로 빈 객체가 생성되고 this에 바인딩된다.

// 2. this에 바인딩되어 있는 인스턴스를 초기화 한다.
  this.radius = radius;
  this.getDiameter = function(){
    return 2 * this.radius;
   };
 }
 
 
 // 3. 완성된 인스턴스가 바인딩된 this가 암묵적으로 반환한다.
 
 //인스턴스 생성 Circle 생성자 함수는 암묵적으로 this를 반환한다.
  const circle1 = new Circle(1); 
  console.log(circle); // Circle {radius: 1, getDiameter:f}
```

여기서 주의할점은 생성자 함수를 만들때 return을 생략하는 것이다. 
생성자 함수 내부에서 명시적으로 this가 아닌 다른 값을 반환하는 것은 생성자 함수의 기본 동작을 훼손하기 때문이다.

#### 내부 메서드 [[Call]]과   [[Construct]]

함수는 객체이므로 일반객체와 동일하게 동작할 수 있다.
함수 객체는 일반 객체가 가지고 있는 내부 슬릇과 내부 메서드를 모두 가지고 있기 때문이다.


```js
// 함수는 객체다
function foo() {}

//함수는 객체이므로 프로퍼티를 소유할 수 있다.
foo.prop = 10;

// 함수는 객체이므로 메서드를 소유할 수 없다.
foo.method = function() {
  console.log(this.prop);
};

foo.method(); // 10
```

함수와 일반 객체와 다른 점은 함수는 호출을 할 수 있다는 것이다. 
따라서 함수 객체는 일반 객체가 가지고 있는 내부 슬롯과 내부 메서드는 물론, 함수로서 동작하기 위해 함수 객체만을 위한 [[Environment]], 등의 내부 슬릇과 [[Call]], [[Construct]]
같은 내부 메서드를 추가로 가지고 있다.

함수가 일반 함수로서 호출되면 함수 객체의 내부 메서드 [[Call]]이 호출되고 
new연산자와 함께 생성자 함수로서 호출되면 내부 메서드 [[Construct]]가 호출된다.




```js
function foo(){}

//일반적인 함수로서 호출 : [[Call]]이 호출된다.
foo();

//생성자 함수로서 호출 : [[Construct]]가 호출된다.
new foo();


```

내부 메서드 [[Call]]을 갖는 함수 객체를 callable이라 하며, 내부 메서드 [[Construct]]를 갖는 함수 객체를 constructor, 
[[Construct]]를 갖지 않는 함수 객체를 non-constructor라고 부른다.

callable은 호출할 수 있는 객체, 즉 함수를 말하며, constructor는 생성자 함수로서 호출할 수 있는 함숫, non-constructor는 객체를 생성자 함수로서 호출할 수 없는 함수를 의미한다.

호출할 수 없는 객체는 함수 객체가 아니므로 함수로서 기능하는 객체, 즉 함수 객체는 반드시 callable이어야 한다. 

모든 함수 객체는 호출할 수 있지만 모든 함수 객체를 생성자 함수로서 호출할 수 잇는 것은 아니다.


constructor: 함수 선언문, 함수 표현식, 클래스
non-constructor: 메서드, 화살표 
