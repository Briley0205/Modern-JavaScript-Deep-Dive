## 17장 생성자 함수에 의한 객체 생성

**TIL(Today I learn) 기록일** : 2022.08.01

- 생성자 함수를 사용하여 객체를 생성하는 방식
- 객체 리터럴을 사용하여 객체를 생성하는 방식과 생성자 함수를 사용하여 객체를 생성하는 방식과의 장단점을 살펴본다.

### 17.1 Object 생성자 함수

- 생성자 함수: new 연산자와 함꼐 호출하여 객체(인스턴스)를 생성하는 함수
- Object 생성자 함수를 사용해 객체를 생성하는 방식은 특별한 이유가 없다면 그다지 유용해 보이지 않는다.

### 17.2 생성자 함수

#### 17.2.1 객체 리터럴에 의한 객체 생성 방식의 문제점

- 객체 리터럴에 의한 객체 생성 방식은 다 하나의 객체만 생성한다. 따라서 동일한 프로퍼티를 갖는 객체를 여러 개 생성해야 하는 경우 매번 같은 프로퍼티를 기술해야 하기 때문에 비효율적이다.

#### 17.2.2 생성자 함수에 의한 객체 생성 방식의 장점

- 프로퍼티 구조가 동일한 객체 여러 개를 간편하게 생성할 수 있다.
- new 연산자와 함께 호출하면 해당 함수는 생성자 함수로 동작한다.

#### 17.2.3 생성자 함수의 인스턴스 생성 과정

- 인스턴스를 생성하는 것과 생성된 인스턴스를 초기화

1. 인스턴스 생성과 this 바인딩
2. 인스턴스 초기화
3. 인스턴스 반환

#### 17.2.4 내부 메서드 [[Call]]과 [[Construct]]

- 함수는 객체이지만 일반 객체와는 다르다. 일반 객체는 호출할 수 없지만 함수는 호출할 수 있다. 따라서 함수 객체는 일반 객체가 가지고 있는 내부 슬롯과 내부 메서드는 몰론, 함수로서 동작하기 위 해 함수 객체만을 위한 내부 슬롯과 내부 메서드를 추가로 가지고 있다.

#### 17.2.5 construct와 non-construct의 구분

- constructor: 함수 선언문, 함수 표현식, 클래스
- non-constructor: 메서드(ES6 메서드 축약 표현), 화살표 함수

- 주의할 것은 생성자 함수로서 호출될 것을 기대하고 정의하지 않은 일반 함수에 new 연산자를 붙여 호출하면 생성자 함수처럼 동작할 수 있다는 것이다.

#### 17.2.6 new 연산자

- 함수를 일반적인 함수로서 호출하면 함수 내부의 this는 전역 개체 window를 가르킨다.

#### 17.2.7 new.target

- new 연산자와 함께 생성자 함수로서 호출되면 함수 내부의 new.target은 함수 자신을 가르킨다. new 연산자없이 일반 함수로서 호출된 함수 내부의 new.target은 undefined다.

- Object와 Function 생성자 함수는 new 연산자 없이 호출해도 new 연산자와 함꼐 호출했을 떄와 동일하게 동작
- String, Number, Boolean 생성자 함수는 
	- new 연산자와 함께 호출했을 때 String, Number, Boolean 객체를 생성하여 반환
	- new 연산자 없이 호출하면 문자열, 숫자, 불리언 값을 반환

---

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔


