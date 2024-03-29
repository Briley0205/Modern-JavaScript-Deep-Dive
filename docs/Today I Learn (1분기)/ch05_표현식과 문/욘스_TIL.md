## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.09

**오늘 읽은 범위** : 5장 표현식과 문

### 사람과 자바스크립트 엔진의 소통 📑

---

### 📖 값

값은 식이 평가되어 생성된 결과를 말한다. 평가란 식을 해석해서 값을 생성하거나 참조하는 것을 의미한다. 예를 들어 `var sum = 10 + 20`이라는 변수가 있을 때, sum 변수엔 `10 + 20`이 아닌, 10 + 20이 평가된 결과인 숫자 `30`이 할당된다.

### 📖 리터럴

리터럴은 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법을 말한다. 다시 말해 사람과 자바스크립트 엔진 사이의 약속이라고 볼 수 있다. 사람이 `function() {}`이라는 함수 리터럴을 입력하면, 자바스크립트 엔진은 이를 평가해 함수 값을 생성한다.

### 📖 표현식

표현식은 값으로 평가될 수 있는 문이다. 평가되어 새로운 값을 생성하거나 기존 값을 참조하게 되면 표현식이다. 위의 리터럴도 값이 평가되기 때문에 표현식이다.

### 📖 문

문은 프로그램을 구성하는 기본 단위이자 최소 실행 단위다. 문의 집합으로 이루어진 것이 바로 프로그램이고, 문을 작성하고 순서에 맞게 나열하는 것이 프로그래밍이다. <br />
문은 여러 토큰으로 구성된다. 토큰이란 문법적인 의미를 가지며, 문법적으로 더 이상 나눌 수 없는 코드의 기본 요소를 의미한다.

### 📖 표현식인 문과 표현식이 아닌 문

표현식은 문의 일부일 수도 있고, 그 자체로 문이 될 수도 있다. 표현식인 문과 표현식이 아닌 문을 구별하는 가장 간단명료한 방법은 변수에 할당해 보는 것이다. 표현식인 문은 값으로 평가되므로 변수에 할당할 수 있다. 하지만 표현식이 아닌 문은 값으로 평가할 수 없으므로 변수에 할당하면 에러가 발생한다.

### 📖 세미콜론

세미콜론은 문의 종료를 나타낸다. 자바스크립트 엔진은 세미콜론으로 문이 종료한 위치를 파악하고 순차적으로 하나씩 문을 실행한다. 하지만 문의 끝에 붙이는 세미콜론은 생략 가능하다. 자바스크립트 엔진이 소스코드를 해석할 때 문의 끝이라고 예측되는 지점에 세미콜론을 자동으로 붙여주는 세미콜론 자동 삽입 기능이 암묵적으로 수행되기 때문이다. <br />
하지만 세미콜론 자동 삽입 기능의 동작이 개발자의 예측과 다를 때가 있어 TC39(ECMAScript 기술위원회)에서는 세미콜론 사용을 권장한다.

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```

```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```

```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```

```

---

### 다른 분이 작성하신 TIL에 대한 소감
