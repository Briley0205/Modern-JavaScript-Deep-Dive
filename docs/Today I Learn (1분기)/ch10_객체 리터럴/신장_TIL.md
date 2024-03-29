## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.16

### 10장 객체 리터럴

#### 10.1 객체란?

- 원시 값을 제외한 나머지 값은 모두 객체다.
- 객체 타입은 다양한 타입의 값을 하나의 단위로 구성한 복합적인 자료구조다.
- 또한, 객체는 변경 가능한 값이다.
- 객체는 0개 이상의 프로퍼티로 구성된 집합이며, 프로퍼티는 키와 값으로 구성된다.
- 객체는 객의 상태를 나타내는 프로퍼티와 프로퍼티를 참조하고 자작할 수 있는 동작을 모두 포함할 수 있기 때문에 상태와 동작을 하나의 단위로 구조화할 수 있어 유용하다.

#### 10.2 객체 리터럴에 의한 객체 생성

- 자바스크립트는 프로토타입 기반 객체지향 언어로서 클래스 기반 객체지향 언어와는 달리 아래의 객체 생성 방법을 지원한다. 
	- 객체 리터럴
	- Object 생성자 함수
	- 생성자 함수
	- Object.create 메소드
	- 클래스(ES6)
- 이러한 객체 생성 방법 중에서 가장 일반적이고 간단한 방법은 객체 리터럴을 사용하는 방법이다. 아래와 같이 객체 리터럴을 이용하여 객체를 생성할 수 있다.

```js
var person = {
	name : 'Lee',
	sayHello: function() {
		console.log(`Hello, My name is ${this.name}.`);
	}
};
```

- 객체 리터럴의 중괄호는 코드 블럭을 의미하지 않는다. 즉, 객체 리터럴을 정의한 다음 ; 을 붙여야 한다.

#### 10.3 프로퍼티

- 객체는 프로퍼티의 집합이며, 프로퍼티를 키와 값으로 구성된다.
- 식별자 네이밍 규칙을 따르지 않는 키에는 반드시 따옴표를 사용해야 한다.
- 문자열 또는 문자열로 평가할 수 있는 표현식을 사용해 프로퍼티 키를 동적으로 생성할 수 도 있다.
- 프로퍼티 키에 문자열이나 심벌 값 외의 값을 사용하면 암묵적 타입 변환을 통해 문자열이 된다.

#### 10.4 메서드

- 프로퍼티 값이 함수일 경우 메서드라 부른다.

#### 10.5 프로퍼티 접근

- 프로퍼티에 접근하는 방법은 2가지 이다.
	- 마침표 프로퍼티 접근 연산자(.)를 사용하는 마침표 표기법
	- 대괄호 프로퍼티 접근 연산자([...])을 사용하는 대괄호 표기법
- 대괄호 프로퍼티 접근 연산자 내부에 지정하는 프로퍼티키는 반드시 따옴표로 감싼 문자열이어야 한다.

#### 10.6 프로퍼티 값 갱신

- 이미 존재하는 프로퍼티에 값을 할당하면 프로퍼티 값이 갱신된다.

#### 10.7 프로퍼티 동적 생성

- 존재하지 않는 프로퍼티에 값을 할당하면 프로퍼티가 동적으로 생성되어 추가되고 프로퍼티 값이 할당된다.

#### 10.8 프로퍼티 삭제

- delete 연산자는 객체의 프로퍼티를 삭제한다.만약 존재하지 않는 프로퍼티를 삭제하면 아무런 에러 없이 무시된다.

#### 10.9 ES6에서 추가된 객체 리터럴의 확장 기능

##### 10.9.1 프로퍼티 축약 표현

- 프로퍼티 값으로 변수를 사용하는 경우 변수 이름과 프로퍼티 키가 동일한 이름일 때 프로퍼티 기를 생략할 수 있다.

##### 10.9.2 계산된 프로퍼티 이름

- 문자열 또는 문자열로 타입 변환할 수 있는 값으로 평가되는 표현식을 사용해 프로피티 키를 동적으로 생성할 수도 있다.단, 프로퍼티 키로 사용할 표현식을 대괄호로 묶어야 한다. 이를 계산된 프로퍼티 이름이라 한다.
- ES5에서 계산된 프로퍼티 이름으로 프로퍼티 키를 동적으로 생성하려면 객체 리터럴 외부에서 대괄호 표기법을 사용해야 한다.
- ES6에서는 객체 리터럴 내부에서도 계산된 프로퍼티 이름으로 프로퍼티 키를 동적 생성할 수 있다.

##### 10.9.3 메서드 축약 표현

- ES5에서 메서드를 정의하려면 프로퍼티 값으로 함수를 할당한다.
- ES6에서는 메서드를 정의할 때 function 키워드를 생략한 축약 표현을 사용할 수 있다. ES6의 메서드 축약 표현으로 정의한 메서드는 프로퍼티에 할당한 함수와 다르게 동작한다. 이에 대해서는 26.2절 "메서드"에서 자세히 살펴보자.

---

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

- 자바스크립트가 객체를 다루는 방법은 매우 혼란스럽다. 동적으로 프로퍼티를 생성해야 할까? 결함이 많이 생길 수 밖에 없을 것 같다. 동적으로 프로퍼티를 생성해야 할 경우가 있을까? 
