## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.25

**오늘 읽은 범위** : 13장 스코프

### 유효범위 📑

- 함수의 매개변수는 함수 몸체 내부에서만 참조할 수 있고 함수 몸체 외부에서는 참조할 수 없다고 했다. 이것은 매개변수를 참조할 수 있는 유효범위, 즉 매개변수의 스코프가 함수 몸체 내부로 한정되기 때문이다.
- 모든 식별자는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효 범위가 결정된다. 이를 스코프라 한다. 즉, 스코프는 식별자가 유효한 범위를 말한다.
- 자바스크립트 엔진은 스코프를 통해 어떤 변수를 참조해야할 것인지를 결정, 즉 식별자 결정identifier resolution을 한다. 따라서 스코프란 자바스크립트 엔진이 식별자를 검색할 때 사용하는 규칙이라고도 할 수 있다.
- 식별자는 어떤 값을 구별할 수 있어야 하므로 유일해야 한다. 그러나 스코프를 통해 식별자인 변수 이름의 충돌을 방지해 같은 이름의 변수를 사용할 수 있게 한다. 스코프는 네임스페이스이므로 한 스코프 내에서 식별자는 유일해야 하지만, 다른 스코프에는 같은 이름의 식별자를 사용할 수 있다.

---

### 스코프의 종류

- 전역과 전역 스코프 - 전역이란 코드의 가장 바깥 영역을 말한다. 전역은 전역 스코프global scope를 만든다. 전역에 변수를 선언하면 전역 스코프를 갖는 전역 변수global variable가 된다. 전역 변수는 어디서든지 참조할 수 있다.
- 지역과 지역 스코프 - 지역이란 함수 몸체 내부를 말한다. 지역은 지역 스코프local scope를 만든다. 지역에 변수를 선언하면 지역 스코프를 갖는 지역 변수local variable가 된다. 지역 변수는 자신이 선언된 지역과 하위 지역(중첩함수)에서만 참조할 수 있다. 즉, 지역변수는 자신의 지역 스코프와 하위 지역 스코프에서 유효하다.

---

### 스코프 체인

- 스코프가 계층적으로 연결된 것을 스코프 체인scope chain이라 한다. 모든 스코프는 하나의 계층적 구조로 연결되며, 모든 지역 스코프의 최상위 스코프는 전역 스코프다.
- 함수는 중첩될 수 있으므로 함수의 지역 스코프도 중첩될 수 있다. 즉 스코프는 함수의 중첩에 의해 계층적 구조를 갖게 된다.
- 변수를 참조할 때 자바스크립트 엔진은 스코프 체인을 통해 변수를 참조하는 코드의 스코프에서 시작하여 상위 스코프 방향으로 이동하며 선언된 변수를 검색identifier resolution한다.
- 자바스크립트 엔진은 하위 스코프로 내려가면서 식별자를 검색하는 일은 없다. 이것은 상위 스코프에서 유효한 변수는 하위 스코프에서 자유롭게 참조할 수 있지만 하위 스코프에서 유효한 변수를 상위 스코프에서 참조할 수 없다는 것을 의미한다.

---

### 함수 레벨 스코프

- var 키워드로 선언된 변수는 오로지 함수의 코드블록(함수 몸체)만을 지역 스코프로 인정한다. 이것을 함수 레벨 스코프function level scope라고 한다.
- 지역스코프는 코드 블록이 아닌 함수에 의해서만 생성된다.
- 대부분의 프로그래밍 언어는 함수 몸체만이 아니라 모든 코드 블록이 지역 스코프를 만든다. 이러한 특성을 블록레벨 스코프block level scope라 한다.

---

### 렉시컬 스코프

- 상위 스코프가 동적으로 변하지 않고 함수 정의가 평가되는 시점에 상위 스코프가 정적으로 결정되는 것을 정적 스코프static scope, 또는 렉시컬 스코프lexical scope라고 한다.
- 대부분의 프로그래밍 언어와 같이 자바스크립트는 렉시컬 스코프를 따른다. 즉, 함수를 어디서 호출했는지가 아니라 함수를 어디서 정의했는지에 따라 상위 스코프를 결정한다. 함수가 호출된 위치는 상위 스코프 결정에 어떠한 영향도 주지 않는다. 함수의 상위 스코프는 언제나 자신이 정의된 스코프다.
- 함수의 상위 스코프는 함수 정의가 실행될 때 정적으로 결정된다. 함수 정의(함수 선언문 또는 함수 표현식)가 실행되어 생성된 함수 객체는 이렇게 결정된 상위 스코프를 기억한다. 함수가 호출될 때마다 함수의 상위 스코프를 참조할 필요가 있기 때문이다.
- 함수를 정의하는 시점에는 함수가 어디서 호출될지 알 수 없고, 함수가 호출되는 시점에 동적으로 상위 스코프를 결정하는 것을 동적 스코프dynamic scope라고 부른다.

---

### 단어장 🔖

```

```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```

```

---

### 다른 분이 작성하신 TIL에 대한 소감
