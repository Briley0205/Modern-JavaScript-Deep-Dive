## 17장 생성자 함수에 의한 객체 생성

**TIL(Today I learn) 기록일** : 2022.08.04

### 17.1 Object 생성자 함수
```
const person = new Object();
```
- 인스턴스: 생성자 함수에 의해 생성된 객체
- 객체를 생성하는 방법은 객체 리터럴을 사용하는 것이 더 간편

### 17.2 생성자 함수

> 객체 리터럴에 의한 객체 생성 방식의 문제점
- 프로퍼티 구조가 동일함에도 불구하고 단 하나의 객체만 생성

> 생성자 함수에 의한 객체 생성 방식의 장점
- 프로퍼티 구조가 동일한 객체를 여러개 생성 가능
- 객체 (인스턴스)를 생성하는 함수

```
function Circle(radius) {
	this.radius = radius;
	this.getDiameter = function () {
		return 2 * this.radius;
	}
}

const circle1 = new Circle(5);
const circle2 = new Circle(10);
```

✅ this 
- this는 객체 자신의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수

<br>

> 생성자 함수의 인스턴스 생성 과정
- 인스턴스를 생성하는 것
- 생성된 인스턴스를 초기화 (인스턴스 프로퍼티 추가 및 초기값 할당)

	✔︎ 1. 인스턴스 생성과 this 바인딩
	- 암묵적으로 생성된 빈 객체, 즉 인스턴스는 this에 바인딩
	- 생성자 함수 내부의 this가 생성자 함수가 생성할 인스턴스를 가리킴

	✔︎ 2. 인스턴스 초기화
	- 함수 내부 처리가 끝나면 완성된 인스턴스가 바인딩된 this 반환
	- this가 아닌 달느 객체를 명시적으로 반환하면 this가 반환되지 못하고 return 문에 명시한 객체가 반환
	- 하지만, 명시적으로 원시 값을 반환하면 원시 값 반환은 무시되고 암묵적으로 this가 반환 (🤔 흥미롭군)
	- this가 아닌 다른 값을 반환하는 것은 생성자 함수의 기본 동작을 훼손, 따라서 생성자 함수 내부에서 return 문은 반드시 생략

<br>

> 내부 메서드 [[Call]] [[Construct]]
- 일반 객체는 호출할 수 없지만 함수는 호출 가능
- 함수가 일반 함수로서 호출되면 함수 객체의 내부 메서드 [[Call]]이 호출
- new 연산자와 함께 생성자 함수로서 호출되면 내부 메서드 [[Construct]]이 호출

> constructor와 non-constructor의 구분
- constructor: 함수 선언문, 함수 표현식, 클래스 (클래스도 함수다)
- non-constructor: 메서드 축약 표현, 화살표 함수

> new 연산자
- new 연산자와 함게 호출하면 생성자 함수로 동작
- 함수 내부 메서드 [[Call]]이 호출되는 것이 아니라 [[Construct]]가 호출
- 호출하는 함수는 non-constructor가 아닌 constructor
- 일반 함수로 호출하면 this는 함수 내부의 전역 객체 window를 가리킴

> new.target
- 메타 프로퍼티
- 함수 내부의 new.target은 함수 자신을 가리킴
- new 연산자 없이 함수로서 호출된 함수 내부 new.target은 undefined

```
- Object, Function 생성자 함수는 new 연산자 없이 호출해도 new 연산자와 함께 호출했을 때와 동일하게 동작
- String, Number, Boolean 생성자 함수는 new 연산자 없이 호출하면 문자열, 숫자, 불리언 값을 반환
```