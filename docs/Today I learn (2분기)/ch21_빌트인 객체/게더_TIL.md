## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.14

**오늘 읽은 범위** : 21장 빌트인 객체

### 빌트인 객체 📑

---

### 자바스크립트의 객체는 크게 3가지

- 표준빌트인
- 호스트
- 사용자정의

### 표준 빌트인 객체 💽

- ECMAScript 사양에 정의된 객체
- 표준 빌트인 객체는 전역 객체의 프로퍼티로 제공되기에 별도의 선언 없이 전역 변수처럼 언제나 참조할 수 있다.
- 표준 빌트인 객체는 생성자 함수이다. 인스턴스를 생성할 수 있다.
- 예외 : Math, Reflect, JSON 빼고...

### 전역 객체 🖼

- 어떤 객체에도 속하지 않는 최상위 객체이다.
- 브라우저 = window
- node.js = global

- 전역 객체는 어떤 객체의 프로퍼티가 되지 않고 표준 빌트인 객체와 호스트 객체를
  프로퍼티로 소유한다.
- 전역객체의 프로퍼티를 참조할때 window, global을 생략할 수 있다.

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
- 계속 객체라고 하니까 객슈탈트붕괴현상이...
- 그치만 객체에 대해 잘 알고나니 map이나 filter를 불필요하게 과도하게 사용하는게 줄어들었다.
```
