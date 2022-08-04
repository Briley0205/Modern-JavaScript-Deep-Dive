## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.08.03-04

### 17장 생성자 함수에 의한 객체 생성 📑
---
### 생성자 함수
new 연산자와 함께 Object 생성자 함수를 호출하면 빈 객체를 생성하여 반환한다. 빈 객체를 생성한 이후 프로퍼티 또는 메서드를 추가하여 객체를 완성할 수 있다.
```js
    const makeObject = new Object();
    // - 빈 객체 생성

    // 프로퍼티 추가하기
    makeObject.text = "put some property";

    console.log(makeObject);
    // 결과 값 : {text : "put some property"}
```
즉 생성자 함수란 new 연산자와 함께 호출하여 객체(<u>인스턴스</u>)를 생성하는 함수를 말한다. 자바스크립트는 다음과 같은 빌트인 생성자 함수를 제공한다.
```js
    // 1. String 생성자 함수에 의한 String 객체 생성
    const strObj = new String("Name");

    // 2. Number 생성자 함수에 의한 Number 객체 생성
    const numObj = new Number("123");

    // 3. Boolean 생성자 함수에 의한 Boolean 객체 생성
    const boolObj = new Boolean(true);

    // 4. Boolean 생성자 함수에 의한 Boolean 객체 생성
    const boolObj = new Boolean(true);

    // 5. Function 생성자 함수에 의한 Function 객체(함수) 생성
    const func = new Function("x", 'return x * x');

    // 6. Array 생성자 함수에 의한 Array 객체(배열) 생성
    const arr = new Array(1, 2, 3);

    // 7. RegExp 생성자 함수에 의한 RegExp 객체(정규 표현식) 생성
    const regExp = new RegExp(/ab+c/i);

    // 8. Date 생성자 함수에 의한 Date 객체 생성
    const date = new Date();
```

---

### 왜 생성자 함수를 사용하는가?
생성자 함수에 의한 객체 생성 방식은 마치 객체(인스턴스)를 생성하기 위한 템플릿(클래스)처럼 생성자 함수를 사용하여 <strong>프로퍼티 구조가 동일한 객체 여러 개를 간편하게 생성할 수 있다.</strong>

---

### 생성자 함수의 인스턴스 생성 과정
1. 인스턴스 생성과 this 바인딩<br>
암묵적으로 생성되는 빈 객체는 생성자 함수가 생성한 인스턴스다. 이 인스턴스는 this에 바인딩된다.
2. 인스턴스 초기화<br>
코드가 실행되면서 this에 바인딩 된 인스턴스에 프로퍼티나 메서드를 추가하고 인수로 전달 받는 초기값을 인스턴스 프로퍼티에 할당한다.
3. 인스턴스 반환<br>
모든 처리가 끝나면 바인딩된 this가 암묵적으로 반환된다.

---

### constructor과 non-constructor
일반 객체는 호출할 수 없지만 함수는 호출할 수 있다. 하지만 함수 객체는 callable이면서 constructor일수도 있고 non-constructor일수도 있다.
- constructor : 함수 선언문, 함수 표현식, 클래스
- non-constructor : 메서드(단, ES6의 메서드 축약 표현만 메서드로 인정한다.), 화살표 함수

즉 이와 같은 구분은 함수가 어디 할당되어 있는지에 따라 메서드인지를 판단하는 것이 아니라 함수 정의 방식에 따라 constructor과 non-constructor를 구분한다.

---

### new 연산자와 new.target
new 연산자와 함께 함수를 호출하면 해당 함수는 생성자 함수로 동작한다. 내부 메서드[[Call]]이 아닌 [[Construct]]가 호출되는 것이다. <br>
반대로 new 연산자 없이 생성자 함수를 호출하면 일반 함수로 호출된다. 이때 내부 메서드는 [[Call]]이 호출된다.
둘 사이에 형식적 차이가 없기 때문에 <u>일반적으로 생성자 함수의 첫 문자는 대문자로 기술한다.(파스칼 케이스 사용)</u>

생성자 함수가 new 연산자 없이 호출되는 실수를 방지하기 위해 ES6에선 new.target을 지원한다.(단 IE는 지원하지 않는다.)<br>
이를 사용하면 new 연산자와 함께 생성자 함수로서 호출되었는지 확인할 수 있다. <strong>이때 함수 내부의 new.target는 함수 자신을 가리킨다.</strong>

---

