## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.18

**오늘 읽은 범위** : 9장 타입 변환과 단축 평가

### 모르면 어렵고 알면 쉬운 것들 📑

#### +간결한 세 줄 요약
- 자바스크립트는 작성자의 의도적인 타입변환 외에 암묵적인 타입변환 기능을 통해 가급적 에러를 일으키지 않도록 표현식을 평가한다.
- 암묵적인 타입변환은 문맥에 따라 문자열, 숫자 타입, 불리언 타입 으로 변환된다. 명시적인 타입변환은 암묵적 타입 변환을 이용하는 것 외에, 표준 빌트인 생성자 함수를 new 연산자 없이 호출하는 방법과 빌트인 메서드를 사용하는 방법이 있다.
- 논리 연산자, 옵셔널 체이닝 연산자, null 병합 연산자를 이용해 표현식에 대한 단축평가를 작성하여 코드를 좀 더 깔끔하게 작성할 수 있다.

---

### 책속 한구절 보관함 📖

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 109  | 동료가 작성한 코드를 정확히 이해할 수 있어야 하고 자신이 작성한 코드도 동료가 쉽게 이해할 수 있어야 한다. |


### 짤막 정리 🔖
```javascript
true || anything // true
false || anything // anything
true && anything // anything
false && anything // false

// -- 논리 연산자를 이용한 if문 대체하기
if (done) message = '완료';
message = done && '완료';

if (!done) message = '미완료';
message = done || '미완료;

// -- 객체를 가리키기를 기대하는 변수가 null 또는 undefined가 아닌지 확인하고 프로퍼티를 참조할 때
// elem이 null이나 undefined와 같은 false 값이면 elem으로 평가되고 아니면 elem.value 값으로 평가.
// null을 호출함으로써 발생하는 에러 방지.
var elem = null;
var value = elem && elem.value; // null
// 이 때 옵셔널 체이닝 연산자 ?. 를 활용 가능
var value2 = elem?.value; // undefined
// ?.은 false 값이더라도 null 또는 undefined가 아니면 우항의 프로퍼티 참조를 이어간다.
var str = '';
var length = str?.length; // 0

// -- 함수 매개변수에 기본값을 설정할 때
// undefined가 할당된 매개변수로 인한 에러 방지
function getStringLenfth(str) {
  str = str || '';
  return str.length;
}
// 혹은 기본값을 실질적으로 부여해도 됨
function getStringLenfth(str = '') {
  return str.length;
}

// -- null 병합 연산자 ??는 변수에 기본값을 설정할 때 유용
var foo = null ?? 'default string'; // 'default string'
// 하지만 좌항의 피연산자가 false로 평가되는 falsy 값(false, undefined, null, 0, -0, NaN, '')이라도 null 또는 undefined가 아니면 좌항의 피연산자를 그대로 반환한다.
var foo = '' ?? 'default string'; // ''

```


---

### 다른 분이 작성하신 TIL에 대한 소감

