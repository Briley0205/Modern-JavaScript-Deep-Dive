## 22장 this

**TIL(Today I learn) 기록일** : 2022.08.17

### 22.1 this 키워드

- this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수다. this를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.
- 자바스크립트의 this는 함수가 호출되는 방식에 따라 this에 바인딩될 값, 즉 this 바인딩이 동적으로 결정된다.

### 22.2 함수 호출 방식과 this 바인딩

- this 바인딩은 함수 호출 방식, 즉 함수가 어떻게 호출되었는지에 따라 동적으로 결정된다.

#### 22.2.1 일반 함수 호출

- 기본적으로 this에는 전역 객체가 바인딩된다.

#### 22.2.2 메서드 호출

- 메서드 내부의 this에는 메서드를 호출한 객체, 즉 메서드를 호출할 때 메서드 이름 앞의 마침표(.) 연산자 앞에 기술한 객체가 바인딩된다.

#### 22.2.3 생성자 함수 호출

- 생성자 함수 내부의 this에는 생성자 함수가 생성할 인스턴스가 바인딩된다.

#### 22.2.4 Function.prototype.apply/call/bind 메서드에 의한 간접 호출

- Function.prototype.apply/call/bind 메서드에 첫번째 인수로 전달한 객체

---

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔


