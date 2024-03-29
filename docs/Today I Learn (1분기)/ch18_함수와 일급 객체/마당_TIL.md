## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.-6

**오늘 읽은 범위** : 18장 함수와 일급 객체

---

### 일급 객체

- 일급 객체의 조건

```
1. 무명의 리터럴로 생성할 수 있다. 즉, 런타임에 생성이 가능하다.
2. 변수나 자료구조(객체, 배열 등)에 저장할 수 있다.
3. 함수의 매개변수에 전달할 수 있다.
4. 함수의 반환값으로 사용할 수 있다.
```

---

### 함수 객체의 프로퍼티

- **함수는 객체다.**
- 따라서 함수도 프로퍼티를 가질 수 있다.
  - arguments : 함수의 인자 (argument)
  - length : 함수를 정의할 때 선언한 매개변수의 개수
  - name : 함수 객체를 가리키는 식별자
  - `__proto__` 접근자: 내부 슬롯이 가리키는 프로토타입 객체에 접근하기 위해 사용하는 접근자 프로퍼티

---

---

### 단어장 🔖

```
hasOwnProperty메서드
인수로 전달받은 프로퍼티 키가 객체 고유의 프로퍼티 키인 경우에만 true를 반환하고 상속받은 프로토타입의 프로퍼티 키인 경우 false를 반환한다.

```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
최근 addEventListener()함수를 다시 알아보다가 알게된건데, addEventListener()의 함수의 두번째 인자는 막연히 "함수"라고 생각하고 있었는데 정확하게는 "객체" 또는 "함수"였습니다. 무슨말인지 잘 몰라서 좀 더 생각해보다가 문득 책에서 함수는 객체라고 했던게 생각났습니다. MDN문서만 보면 두번째 인자의 타입만 설명하고 구체적으로 addEventListener()가 어떻게 동작하는지에 대해서는 나와있지 않은데, 오늘 내용과 연계해서 살펴보면 좋지않을까 싶네요.

```

---
