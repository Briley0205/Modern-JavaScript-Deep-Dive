## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : 2022.07.12-13

**오늘 읽은 범위** : 6장, 데이터 타입

### 자바스크립트의 데이터 타입(Type)

➡️데이터 타입은 7가지가 있다.(ES6 기준) <br>
➡️**원시 타입**, **객체 타입**으로 나눈다.

|   구분    |                 데이터 타입                 |
| :-------: | :-----------------------------------------: |
| 원시 타입 | 숫자, 문자열, 불리언, undefined, null, 심벌 |
| 객체 타입 |             객체, 함수, 배열 등             |

### 원시 타입

`숫자 타입 number`<br>
단 하나의 숫자 타입만 존재. 모든 수를 실수로 처리한다. 추가적으로 아래처럼 표현도 가능하다.

- Infinity(양의 무한대)
- -Infinity(음의 무한대)
- NaN(산술 연산 불가 Not a number)

`문자열 타입 string`<br>
텍스트 데이터를 나타날 때 사용. UTF-16의 집합이며 전 세게 대부분 문자 표현이 가능하다. 작은따옴표(''), 큰따옴표(""), 백틱(``)으로 감싸서 사용한다.

`불리언 타입 boolean`<br>
논리적 참, 거짓. true와 false만 있다.

`undefined 타입`<br>
var 키워드로 선언한 변수는 undefined로 초기화된다. 즉 변수 선언 후 값을 할당하기 않은 변수를 참조시 undefined가 반환됨.

`null 타입`<br>
변수에 값이 비어있음을 의도적으로 명시한 것. 즉 변수에 null 할당시 이전에 쓰던 값은 더 이상 참조하지 않게 된다.

`심벌 타입 symbol`<br>
변경 불가능한 원시 타입의 값. 다른 타입과 중복되지 않는 유일무이한 값. 충돌 위험 없는 객체 유일 프로퍼티 키를 만들기 위해 사용한다.

# 객체 타입

## 위의 6가지 원시 타입 데이터 타입 제외의 값은 모두 다 객체 타입이다. (EX. 함수, 배열 등)

### 책속 한구절 보관함 📖

> p. 71 <br>
> 정적 타입 언어는 변수의 타입을 변경할 수 없으며, 변수에 선언한 타입에 맞는 값만 할당할 수 있다. <br>
> 자바스크립트는 정적 타입 언어와 다르게 변수를 선언할 때 타입을 선언하지 않는다. 다만 var, let, const 키워드를 사용해 변수를 선언할 뿐이다. <br>

> p.73<br>
> ❕변수는 꼭 필요한 경우에 한해 제한적으로 사용한다. 변수의 무분별한 남발은 금물이며, 필요한 만큼 최소한으로 유지하도록 주의해야한다. <br>
> ❕변수의 스코프는 최대한 좁게 만들어 변수의 부작용을 억제해야한다. <br>
> ❕전역 변수는 최대한 사용하지 않도록 한다. <br>
> ❕변수보다는 상수를 사용한다.<br>
> ❕변수 네이밍은 변수 목적이나 의미를 파악할 수 있도록 한다.

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
부동소수점 형식이란?
소수점의 위치가 바뀌기 때문에 실수 표현시 주로 사용. 실수를 부동 소수점 방식으로 저장시 부호 비트, 지수 부분, 가수 부분 이렇게 총 세 영역으로 저장이 된다.


동적 타이핑이란?
데이터 타입을 컴파일이 아닌 런타임 시 결정하는 것으로, 데이어 타입의 명시 없이 변수명만 가지로 선언 및 값을 전달하는 것이 가능하다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
정적 타입과 동적 타입의 차이에 대해 알고 짚어갈 수 있어서 좋았다. 동적 타입 언어라 하면 편리함이 더 크다고 생각했는데, 이번 챕터를 읽으며 동적 타입의 단점과 그렇기에 조심해야하는 부분도 알게 되는 기회를 가졌다. 자바스크립트는 유연하지만 자유로운 것 같으나 마냥 신뢰만 해서는 안 되는 언어 같다.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
심볼이 객체에서 유일무이한 프로퍼티, 키를 위해 사용한다고 했는데 어떻게 사용되는지 궁금하다. 개념적으로는 알겠으나 쓰임새는 더 찾아봐야할듯하다.
```
