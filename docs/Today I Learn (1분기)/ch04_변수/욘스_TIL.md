## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.06

**오늘 읽은 범위** : 4장 변수

### 값의 위치를 가리키는 상징적인 이름, 변수 📑

---

### 변수(Variable)란?

- 하나의 값을 저장하기 위해 확보한 메모리 공간 자체, 또는
  그 메모리 공간을 식별하기 위해 붙인 이름. 즉, 프로그래밍 언어에서 값을 저장하고 참조하는 메커니즘으로, 값의 위치를 가리키는 상징적인 이름이다.
- 변수 이름을 식별자라고도 한다. 식별자는 어떤 값을 구별해서 식별할 수 있는 고유한 이름으로, 값이 아닌 메모리 주소를 기억한다. 그러나 변수 이름에만 국한하지 않고 함수, 클래스 등 메모리 상에 존재하는 어떤 값을 식별할 수 있는 이름은 모두 식별자라고 부른다.

</br>

---

</br>

## 변수 동작 순서

### 1. 선언

- 변수 선언이란 값을 저장하기 위한 메모리 공간을 확보하고, 변수 이름과 확보된 메모리 공간의 주소를 연결해서 값을 저장할 수 있게 준비하는 것 - 즉 변수를 생성하는 것을 말한다.
- 변수 선언에 의해 확보된 메모리 공간은 확보가 해제되기 전까지는 누구도 확보된 메모리 공간을 사용할 수 없도록 보호되므로 안전하게 사용할 수 있다.
- 변수를 사용하려면 반드시 선언이 필요하다. 변수를 선언할 때는 var, let, const 키워드를 사용한다. 만약 선언하지 않은 식별자에 접근하면 ReferenceError가 발생한다.

### 2. 초기화

- 일반적으로 초기화란 변수가 선언된 이후 최초로 값을 할당하는 것을 말한다. 만약 초기화 단계를 거치지 않으면 확보된 메모리 공간에는 이전에 다른 애플리케이션이 사용했던 값(쓰레기 값)이 남아있을 수 있다.
- var 키워드를 사용한 변수 선언은 선언 단계와 초기화 단계가 동시에 진행되고, undefined로 암묵적인 초기화가 자동 수행된다.

### 3. 실행 시점과 호이스팅

- 변수 선언은 소스코드가 한 줄씩 순차적으로 실행되는 시점인 런타임이 아니라 그 이전 단계에서 먼저 실행된다.
- 자바스크립트 엔진은 소스코드를 실행하기에 앞서 먼저 소스코드의 평가 과정을 거치면서 소스코드를 실행하기 위한 준비를 한다. 이 평가과정에서 자바스크립트 엔진은 변수 선언을 포함한 모든 선언문을 소스코드에서 찾아내 먼저 실행한다.
- 즉 자바스크립트 엔진은 변수 선언이 소스코드의 어디에 있든 상관없이 다른 코드보다 먼저 실행된다. 따라서 변수 선언이 소스코드의 어디에 위치하는지와 상관없이 어디서든지 변수를 참조할 수 있다.
- 변수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징을 변수 호이스팅이라 한다. 변수 선언 뿐 아니라 var, let, const, function 등의 키워드를 사용해 선언하는 모든 식별자 역시 호이스팅된다.

### 4. 할당

- 변수 선언은 소스코드가 순차적으로 실행되는 시점인 런타임 이전에 먼저 실행되지만, 값의 할당은 소스코드가 순차적으로 실행되는 시점인 런타임에 실행된다.

### 5. 값의 재할당

- 재할당은 변수에 저장된 값을 다른 값으로 변경한다. 그래서 변수라고 한다.
- 값을 재할당 할 수 없어서 변수에 저장된 값을 변경할 수 없다면 변수가 아니라 상수라 한다. 상수는 한번 정해지면 변하지 않는 값이다.

</br>

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```

```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
얼마전 var, let, const의 차이에 대해 공부하며 변수가 선언되기 전에 변수를 참조해도 에러가 뜨지 않고 undefined라고 나오는 것을 보고 의문이 생겼었다. 그 당시엔 공부가 부족해 혹시 var는 선언과 동시에 초기화가 이루어지기 때문에, 또 스코프가 함수레벨이기 때문에 그런걸까 하고 막연히 잘못된 방향으로 생각했었다.
let이나 const로 선언한 식별자도 에러가 뜨지 않았지만 그 이유에 대해서는 딱히 설명할 방법이 없어 그냥 넘어가야만 했었다.

그때 가졌던 의문이 오늘 드디어 풀렸다! 초기화되기 때문도 아니고, 스코프의 범위 문제도 아니었다. 모든 선언문은 런타임 이전 단계에서 먼저 실행되기 때문이었다.

공부가 마치 퍼즐조각 맞춰지듯 채워지고 있어서 재밌고 즐겁다.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```

```

---

### 다른 분이 작성하신 TIL에 대한 소감

```

```
