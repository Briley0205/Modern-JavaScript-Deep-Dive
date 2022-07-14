## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.14

**오늘 읽은 범위** : 7장 연산자

### JS 연산자 탐구생활 📑

- 모든 연산자는 새로운 값을 만들어낸다.
- 이 과정에서 의도치않게 타입이 강제 변환되는 경우도 있다.
- 일부 연산자는 다른 코드(또는 피연산자)에 영향을 주는 부수 효과가 있다.

---

### 단어장 🔖
```js
연산자(operator)
> true && false 
false라는 값을 생성하는 논리 연산자

연산자는 값으로 평가된 피연산자(operand)를 연산해 
새로운 값을 만든다.
```
```js
산술 연산자(arthmetic operator)
> 이항 산술 연산자
>> 5 * 2 // 10

두 개의 피연산자를 산술 연산하여 숫자 값을 만든다.

> 단항 산술 연산자
>> let i = 10; console.log(i++) // 11
>> let n = '3'; console.log(+n); // 3

+ 증가/감소(--/++) 연산자는 피연산자의 값을 암묵적으로 변경한다.
또한, 전후 위치에 따라 연산이 수행되는 시점이 달라진다.
&& 단항 연산자는 다른 데이터 타입을 숫자로 타입 변환한다.
```
```js
let volume = 50;
volume /= 5; // 10

위 예제는 우항(피연산자)의 평가 결과를 좌항(식별자)에 할당한다.
연산 결과를 변수에 할당하는 것을 `할당 연산자`라고 한다.

> 비교 연산자
true != false // true
17 == '17' // false

let volume = 50;
volume >= 30 && volume < 70 // true

> 삼항 조건 연산자
let index = 6;
index < 10 ? 0 : index - 5;

> 논리 연산자
true && false // false
!false // true

> 지수 연산자
5 **= 2 // 5의 제곱(2승) -> 25
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

> null과 undefined는 어떤 값인가?

null은 <strong>값이 없음을 의도적으로 명시할 때 쓰는</strong> `값`이고,</br>
undefined는 <strong>값이 주어지지 않았을 때 사용하는</strong> `값`이다.

```js
let x = true;
console.log(x - 1); // 0

let x = false;
console.log(x - 1); // -1

let x = null;
console.log(x - 1); // -1
console.log(typeof x) // object

let x = undefined;
console.log(x - 1); // NaN
console.log(typeof x); // undefined

null은 원시 데이터타입으로, 객체이고 참조 자료형이다.
(null이 빈 참조를 나타내는 데 자주 사용되기 때문)
```
동등 비교(==) 사용시 주의할 점</br>
```js
> 의도치않은 타입 변환이 일어날 수 있다.
> 피연산자 중 하나가 true / false 라면 예측하기 어려운 결과를 만든다.
 '0' == false; // true

따라서, 동등 비교 연산자(==) 대신, 일치 비교 연산자(===)를 사용하는 편이 좋다.
```

---

### 다른 분이 작성하신 TIL에 대한 소감

