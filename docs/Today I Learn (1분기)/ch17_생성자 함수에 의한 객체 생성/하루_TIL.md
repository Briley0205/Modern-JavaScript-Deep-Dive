## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.04

**오늘 읽은 범위** : 17장 생성자 함수에 의한 객체 생성

---

## 객체 리터럴과 Object 생성자 함수의 차이

### 1. 객체 리터럴

- 객체 생성의 5가지 방법 중 객체 리터럴을 통한 생성이 가장 일반벅이고 간단한 방식이다.
- 객체 리터럴 방식은 key : value 형식의 data 를 직접 입력하는 방식이다.

```jsx
const Obj = {
	key: value
}
```

### 2. Object 생성자 함수

- new 연산자와 함께 Object 생성자 함수를 호출하면 빈 객체를 생성하여 반환한다.
- key, value 는 빈 객체에 추가하여 객체를 완성한다.

```jsx
const obj = new Object();

obj.key = `value`
```

- 객체 리터럴을 통한 객체 생성보다 비효율적임으로 일반적인 상황에선 사용할 이유가 없다.

</br>

## 생성자 함수

### 1. 생성자 함수의 쓰임새(장점)

동일한 프로퍼티를 갖는 객체를 여러 개 생성해야 하는 경우

- 객체 리터럴에 의한 생성 방식의 경우 동일한 프로퍼티를 갖는 객체를 여러 개 생성할 경우 같은 프로퍼티를 가진 객체를 다수 기술해야한다.
- 생성자 함수에 의한 객체 생성 방식은 마치 객체를 생성하기 위한 템플릿 처럼 생성자 함수를 사용할 수 있다.

```jsx
// 생성자 함수
function Circle(radius) {
  // 생성자 함수 내부의 this는 생성자 함수가 생성할 인스턴스를 가리킨다.
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

// 인스턴스의 생성
const circle1 = new Circle(5);  // 반지름이 5인 Circle 객체를 생성
const circle2 = new Circle(10); // 반지름이 10인 Circle 객체를 생성

console.log(circle1.getDiameter()); // 10
console.log(circle2.getDiameter()); // 20
```

### 2. 생성자 함수의 인스턴스 생성 과정

- 인스턴스 생성과 this 바인딩
    - 암묵적으로 빈 객체 생성, 빈 객체는 생성자 함수가 생성한(할) 인스턴스이다. 이 빈 객체는(인스턴스) 는 this에 바인딩 된다.
    - 이 처리는 런타임 이전에 실행된다.
- 인스턴스 초기화 (추가 이해 필요)
- 인스턴스 반환
    - 생성자 함수 내 모든 처리가 끝나면 완성된 인스턴스가 바인딩된 this 로 부터  암묵적으로 반한된다.
    - 만일 명시적으로 return 문을 통해 반환하면 this 가 반환되지 못한다.
    
```jsx
function Circle(radius) {
  // 1. 암묵적으로 인스턴스가 생성되고 this에 바인딩된다.

  // 2. this에 바인딩되어 있는 인스턴스를 초기화한다.
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };

  // 3. 완성된 인스턴스가 바인딩된 this가 암묵적으로 반환된다
}

// 인스턴스 생성. Circle 생성자 함수는 암묵적으로 this를 반환한다.
const circle = new Circle(1);
console.log(circle); // Circle {radius: 1, getDiameter: ƒ}
```

</br>

### 3. 내부 메서드 [[Cal]] 과 [[Construct]]

- 함수는 객체이나 호출할 수 있다는 특징이 있다.따라서 다른 객체가 가지고 있는 내부 슬롯과 내부 메서드는 물론, 함수 객체만을 위한 내부 슬롯과 내부 메서드도 가지고 있다.
- 함수를 위한 내부 메소드로는 [[Cal]] 과 [[Construct]] 이 있는데, 모든 함수 객체는 [[Cal]] 을 가진다. 하지만 모든 함수가 [[Construct]]  를가지진 않는다.
- [[Construct]] 을 가지는 객체와 가지지 않는 객체를 constructor, non-constructor 이라 나누는데, 둘의 차이는

```
constructor : 일반 함수 또는 생성자 함수로서 호출할 수 있는 객체
non-constructor : 일반 함수로서만 호출할 수 있는 객체 

constructor : 함수 선언문, 함수 표현식, 클래스
non-constructor : 메서드(es6 메서드 축약 표현), arrow function
```

</br>

### 4. new 연산자

- 일반 함수와 생성자 함수에는 형식적 차이가 없다. 그럼으로 생성자 함수를 new 연산자 없이 호출할 수도 있고 일반 함수를 new 연산자와 함께 호출할 수도 있다.
- 이러한 실수를 줄이기 위해 es6 에서는 new.target을 지원한다.
    - new.target은 아래와 같이 사용 가능함
    
    ```
    // 생성자 함수
    function Circle(radius) {
      // 이 함수가 new 연산자와 함께 호출되지 않았다면 new.target은 undefined다.
      if (!new.target) {
        // new 연산자와 함께 생성자 함수를 재귀 호출하여 생성된 인스턴스를 반환한다.
        return new Circle(radius);
      }
    
      this.radius = radius;
      this.getDiameter = function () {
        return 2 * this.radius;
      };
    }
    
    // new 연산자 없이 생성자 함수를 호출하여도 new.target을 통해 생성자 함수로서 호출된다.
    const circle = Circle(5);
    console.log(circle.getDiameter());
    ```
