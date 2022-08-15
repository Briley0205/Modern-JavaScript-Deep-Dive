## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.15

**오늘 읽은 범위** : 22장 this

### this 키워드

---

this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수다. 
this를 통해 자신이 속한 객체 또느 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.


this는 자바스크립트 엔진에 의해 암묵적으로 생성된다. 
this 바인딩은 함수 호출 방식에 의해 동적으로 결정된다. 

```js
const circle = {
  radius: 5,
  getDiameter() {
    reuturn 2 * this.radius;
    }
}
console.log(circle.getDiameter()); // 10
```
```js
fucntion Circle(radius) {
  this.radius =radius;
}
Circle.prototype.getDiameter = function (){
  return 2 + this.radius;
};

const circle = new Circle(5);
console.log(circle.getDiameter()); // 10
```
첫 번째 예제처럼 객체 리터럴의 메서드 내부에서의 this는 메서드를 호출한 객체, 즉 circle을 가리키고
두 번째 예제처럼 생성자 함수 내부의 this는 생성자 함수가 생성할 인스턴스를 가리킨다. 

---
### 함수 호출 방식과 this 바인딩
---
this 바인딩은 함수 호출 방식, 즉 함수가 어떻게 호출 되었는지에 따라 동적으로 결정된다.

this 바인딩은 함수 호출 시점에 결정된다. 

---
#### 일반 함수 호출

기본적으로 this에는 전역 객체가 바인딩 된다.

---
#### 메서드 호출

메서드를 호출할 때 메서드 이름 앞의 마침표(.) 연산자 앞에 기술한 객체가 바인딩된다. 

```js
const person = {
  name: "Lee",
  getName() {
    return this.name;
    }
};
console.log(person.getName()); // Lee
```
#### 생성자 함수 호출

생성자 함수 내부의 this에는 생성자 함수가 (미래에) 생성할 인스턴스가 바인딩 된다.

```js
//생성자 함수
function Circle(radius) {
  this.radius =radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  }
}

const circle1 = new Circle(5);
const circle2 = new Circle(10);

console.log(circle1.getDiameter()); // 10
console.log(circle2.getDiameter()); // 20
```

만약 new 연산자와 함께 생성자 함수를 호출하지 않으면 생성자 함수가 아니라 일반 함수로 동작한다. 
```js
//new 연산자와 함께 호출하지 않으면 생성자 함수로 동작하지 않는다 즉, 일반적인 함수의 호출이다.

const circle3 = Circle(15);
console.log(circle3); // undefined 

```

---
