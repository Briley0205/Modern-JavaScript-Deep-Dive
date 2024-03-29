## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.06

**오늘 읽은 범위** : 4장 변수

### 메모리에 붙이는 꼬리표, 변수(식별자) 📑

---

### 변수란?

컴퓨터의 해석 및 실행 방식은 사람과 유사하면서 다르다.</br>
메모리에 데이터를 저장하고, CPU를 사용해 연산한다. 이 때 만들어낸</br> 결과 값을 꺼내어 재사용 하기 위해 메모리 공간에 붙이는 식별자를 변수라 한다.

</br>

> 값이 저장될 메모리 주소는 코드가 실행될 때 메모리 상황에 따라 임의로 결정된다.

같은 컴퓨터, 같은 프로그램이라 하더라도, <strong>매번 실행될 때마다 다른 메모리에 저장</strong>된다.</br> 때문에 메모리 주소를 통해 값에 직접 접촉하려 하는 것은 무모하다.</br>
그래서 평가 결과값을 저장하고, 참조하기 위해 값의 위치를 가리키는 상징적인 이름을 붙여 관리한다.

---

### 변수 생성 시 일어나는 과정

</br>
JS엔진이 변수 키워드를 발견하면,

1. 값을 저장하기 위한 메모리 공간을 확보
2. 변수 이름과 메모리 공간의 주소를 연결
3. 변수 이름을 실행 컨텍스트에 등록
4. 메모리 공간에 undefined를 할당해 초기화

하는 과정을 거친다.

> 초기화 단계를 거치는 이유 ?

메모리 공간을 확실히 비워놓기 위해 초기값을 설정한다.</br>
그렇지 않으면, 이전에 실행한 다른 앱에서 남겨진 값(쓰레기 값)이</br>
아직 메모리에 남아있을 가능성이 있기 때문이다.

---

### JS는 코드 실행을 위한 평가 과정을 거친다

</br>
변수 선언은, 런타임이 아닌, 평가 단계에서 먼저 실행된다.</br>
JS는 코드를 실행하기에 앞서 소스코드 평가 과정을 거친다.</br>
바로 이 단계에서, 모든 선언문을 찾아 먼저 실행해 놓는다.</br> 
때문에 (var의 경우)변수 선언이 어느 라인에 위치하든,</br> 
어디서든 변수를 참조할 수 있다.</br>
(const, let은 이를 용납하지 않는다.)

var : undefined</br>
const, let: RefrenceError

> 값의 할당 시점

모든 선언문은 평가 단계에서 먼저 실행된다.</br>
하지만 값의 할당은 런타임에 이루어진다.</br>

또한, JS 엔진은 변수의 선언(등록)과 값의 할당을</br>
2개의 문으로 나누어 하나씩 실행한다.</br>
때문에 변수에 undefined를 할당하고 초기화 시킨다는 것은 변함없다.

> 값의 재할당

이미 선언된 변수에 값을 재할당 하면, 처음 할당했을 당시</br>
확보했던 메모리에 저장된 값을 수정하는 것이 아니라,</br>
또다른 메모리 공간을 확보한 후, 그 메모리 공간에 새로운 값을 저장한다.</br>

그리고 이전 값은 어떤 변수와도 연결되어 있지 않은 상태가 된다.</br>
어떤 식별자와도 연결되어 있지 않은 값은 불필요해 진다.</br>
따라서 이러한 값들은 가비지 콜렉터에 의해 메모리에서 해지된다.

---

### 단어장 🔖
```
 할당(대입, 저장): 변수에 값을 저장함

 매핑: 하나의 값을 다른 값으로 대응시키는 것

 변수 호이스팅: 변수 선언문이 코드의 맨 앞줄로 끌어올려진 것처럼
 동작하는 것.

 가비지 콜렉터: 메모리 공간을 주시하며 더 이상 사용되지 않는
 메모리의 값을 헤제하는 기능.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔
```
선언된 모든 식별자가 호이스팅된다.
그럼, 이건 왜 그럴까
var 의 경우:
console.log(score); --> undefined
var score;

const, let의 경우:
console.log(score); --> ReferenceError(참조 에러)
const(or let) score = 1;

var, const, let이 실행 전 평가 단계에서 먼저 실행되고,
초기값을 undefined로 받으며, 호이스팅 된다면,
왜 모두 undefined로 출력되는 것이 아니라,
const, let에서는 참조 에러가 나는 것일까 ?

이유는, TDZ(temporal dead zone) 때문이다.
TDZ는 const와 let, class의 유효성을 관리한다.
따라서 선언 전에 변수에 접근하는 것을 금지하며,
변수 선언 전에는 그 어떠한 기능도 사용할 수 없다.

전자의 경우, const(or let) score = 1; 구문 전 줄 까지
score 변수는 TDZ에 들어있기 때문에 
선언 전에 변수를 호출하지 못하는 것이다.

```

---

### 다른 분이 작성하신 TIL에 대한 소감

