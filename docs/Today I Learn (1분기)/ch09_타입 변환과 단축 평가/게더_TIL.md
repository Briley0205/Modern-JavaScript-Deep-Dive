## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.18

**오늘 읽은 범위** : 9장 타입 변환과 단축 평가

### 자바스크립트의 타입 변환 📑

- 자바스크립트는 상황에 따라 엔진 스스로 타입을 바꿔버리는 기능이 있다.
- 개발자가 명시적으로 변경할 수도 있다.
- 마치 사람이 숨쉬는 걸 인식해서 완급을 조절해 쉴 수 있는 것처럼.
- 지금 막 자동이 수동으로 변경되었을 것이다.
- 😆

---

### 타입 강제 변환

- 변수에 숫자를 지정하고 문자열 연결 연산자 + 를 사용하면 해당 연결을 사용해 만든 식은 문자열 타입이 된다.
- 변수에 숫자를 ''문자열 형식으로 지정하고 숫자 연산자를 사용하면 해당 연결을 사용해 만든 식은 숫자 타입이 된다.
- 피연산자 또는 표현식이 불리언 타입이어야 할때 0과 1, 값이 있는 애 등을 불리언으로 치환할 수 있다.

- 변수 자체가 바뀌는 것은 아니다.

### 명시적 타입 변환(explicit coercion) / 타입 캐스팅(type casting)

- 생성자 함수를 new없이 호출하면 명시적으로 타입이 바뀐다.
- toString 메서드를 사용할 수 있다.
- parseInt 메서드를 사용할 수 있다.
- 문자열 연결 연산자를 사용할 수 있다.
- 산술 연산자를 사용할 수 있다.
- !부정논리 연산자를 사용할 수 있다.

---

### 단축 평가

- 논리연산자를 사용하면 타입을 or로 평가할 수 있다.
- &&, ||
- 삼항연산자도 논리연산자
- 타입이 다른거일때나, undefined일때도 오류가 나지 않게 해준다.
- 옵셔널체이닝 연산자도 여기에 들어간다.

- 솔직히 리액트에서 제일 많이 쓴다.

---

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
타입스크립트는 팀프로젝트로 할때 참 좋은 것 같다.
나혼자 한땀한땀 작성하는 것은
무척 귀찮고 힘들고 오류의 산을 건너는 듯한 일이지만...
다같이 하면 훨씬 빨리, 객관적으로 지치지 않고 끝낼 수 있으며!
일단 빌드해놓으면 그 다음부터는 무척 편하게 쓸 수 있다.

물론 오류는 그 이후에도 끊임없이 발생한다.
타입ai 같은게 vsCode extension으로 있으면 좋겠다.
```

---

### 다른 분이 작성하신 TIL에 대한 소감

```
언제나 성실하게 작성해주시는 분들 멋져여!
```
