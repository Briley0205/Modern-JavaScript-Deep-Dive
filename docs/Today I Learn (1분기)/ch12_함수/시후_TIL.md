## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.22

**오늘 읽은 범위** : 12장 함수

### 함수 대백과사전 📑

- 함수 리터럴 또한 평가되어 값(객체)을 생성하기에, 함수는 객체다.
- 함수 리터럴은 코드의 문맥에 따라 표현식인지 아닌지가 결정된다. 따라서 중의적 표현이다.
- JS 함수는 일급 객체이기 때문에 함수를 값처럼 자유롭게 사용할 수 있다.

---

|  | 함수 선언문 | 함수 표현식 |
|----|-------------|----------|
| 함수 이름 | 생략할 수 없다 | 생략할 수 있다 |
| 표현식 | 표현식이 아닌 문 | 표현식인 문 |
| 호출 방식 | 외부 호출 가능 | 몸체 외부 호출 불가 |
| 생성 시점 | 평가단계 생성 (객체로 초기화) | 런타임 생성 (undefined로 초기화) |
| 호이스팅 | 함수 호이스팅 | 변수 호이스팅 |

### 함수 선언문을 몸체 외부에서 호출할 수 있는 이유? 🔎

> 함수는 함수 이름으로 호출하는 것이 아니라 함수 객체를 가리키는 `식별자`로 호출한다.

다음 함수 선언문은 표현식이 아닌 문이다.</br>

```js
function kakaopay() {} ---> let kakaopay = function kakaopay() {} // 함수 객체 할당

kakaopay(); // js가 암묵적으로 생성한 식별자로 호출
```
함수 리터럴 내부의 함수 이름은 함수 몸체 내에서만 참조할 수 있는 식별자다.</br>
이론상으로, <strong>함수 몸체 외부에서 호출할 수 없다</strong>는 말이다.

</br>
하지만, 자바스크립트 엔진은 생성된 함수를 호출하기 위해</br>
함수 이름과 동일한 식별하를 암묵적으로 생성하고,</br> 
거기에 함수 객체를 할당한다.</br>

---

### 인수의 전달 과정 🕯

함수 실행 시 인수가
|  | 원시 값일 경우 | 객체 값일 경우 |
|--|---------------|----------------|
| 전달 방식 | 값에 의한 전달 | 참조에 의한 전달 |
| 내용물 변경 | 새로운 원시 값으로 교체 | 참조 값 전달로 원본 객체 변경 |

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```js
일급 객체 : 값의 성질을 갖는 객체
---> 함수는 일급 객체(함수 표현식)

생성자 함수 : 객체를 생성하는 함수
```

### 책속 한구절 보관함 📖

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 162 | 자바스크립트 엔진은 생성된 함수를 호출하기 위해 함수 이름과 동일한 이름의 식별자를</br> 암묵적으로 생성하고, 거기에 함수 객체를 할당한다. |
| 163 | 함수는 함수 이름으로 호출하는 것이 아니라 함수 객체를 가리키는</br> 식별자로 호출한다. |

