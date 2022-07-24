### Quiz

1.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
console.log("Cat" && "Dog");
console.log("Cat" || "Dog");

var elem = null;
var value = elem && elem.value;
console.log(value);
value = elem?.value;
console.log(value);

var str = "";
var length1 = str && str.length;
var length2 = str?.length;
console.log(length1, length2);
```

2."값에 의한 전달"와 "참조에 의한 전달"을 설명하고, 자바스크립트의 전달 방법을 기술하라.

3.아래 코드의 결과를 예상하고 이유를 설명하라.

```javascript
var person1 = {
  name: "Lee",
};

var person2 = {
  name: "Lee",
};

console.log(person1 === person2);
console.log(person1.name === person2.name);

person1 = person2;
console.log(person1 === person2);
```

4.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
var a = {};
var func = function (b) {
  b = b.a = 1;
  b.b = 2;
};
func(a);
console.log(a);
```

5."얕은 복사"와 "깊은 복사"를 설명하고, 자바스크립트에서 깊은 복사를 구현하는 방법을 설명하라.(라이브러리 사용)

6.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
function changeVal(primitive, person) {
  primitive += 100;
  person.name = "Kim";
}

var primitive = 100;
var person = { name: "Lee" };

console.log(primitive);
console.log(person);

changeVal(primitive, person);

console.log(primitive);
console.log(person);
```

#### 해설 및 풀이

### 1번

```jsx
// "Cat"이 암묵적 타입 변환으로 True판정이기 때문에 "Dog"가 출력됩니다.
console.log("Cat" && "Dog"); // Dog
// 1번과 마찬가지로 "Cat"이 True이므로 True의 출력값인 "Cat" 이 출력됩니다.
console.log("Cat" || "Dog");

var elem = null;
var value = elem && elem.value;
// 객체를 가리키기를 기대하는 변수의 값이 null이기 때문에 타입 에러가 발생한다.
// 이 때 단축 평가를 사용하면 에러를 발생시키지 않는다.
console.log(value); // null
value = elem?.value;
// 좌항의 피연산자가 null이므로 undefined를 반환한다.
console.log(value); //undefined

var str = "";
// length1은 falsy값
var length1 = str && str.length;
// length2는 str가 null또는 undefined가 아니므로 우항을 출력한다.
var length2 = str?.length;
console.log(length1, length2); // 0
// length1은 falsy이므로 아무것도 출력되지 않는다.
```

### 2."값에 의한 전달"와 "참조에 의한 전달"을 설명하고, 자바스크립트의 전달 방법을 기술하라.

값에 의한 전달 : 원본 값을 복사해온다. 원본 값의 변화에 영향을 받지 않는다.
참조에 의한 전달 : 원본 값의 메모리 주소를 복사해온다. 원본 값의 변화에 영향을 받는다.

자바스크립트에는 참조에 의한 전달은 존재하지 않고 값에 의한 전달만이 존재한다.

### 3.아래 코드의 결과를 예상하고 이유를 설명하라.

```javascript
var person1 = {
  name: "Lee",
};

var person2 = {
  name: "Lee",
};

// 둘 다 타입은 객체이지만 다른 객체이므로 false를 반환한다.
console.log(person1 === person2); // false
// 타입은 스트링, 값도 같으므로 true이다.
console.log(person1.name === person2.name); // true

person1 = person2;
// 원본과 사본 모두 동일한 객체를 가르키게 된다.
console.log(person1 === person2); // true
```

### 4.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
var a = {};
var func = function (b) {
  // 인수로 받은 a는 프로퍼티가 없었으나 아래의 행에서 a : 1이라는 프로퍼티를 생성
  b = b.a = 1;
  b.b = 2;
};
func(a);
console.log(a); //1
```

### 5."얕은 복사"와 "깊은 복사"를 설명하고, 자바스크립트에서 깊은 복사를 구현하는 방법을 설명하라.(라이브러리 사용)

얕은 복사 : 한단계까지만 복사하는 것
깊은 복사 : 객체에 중첩되어 있는 객체까지 모두 복사하는 것

깊은 복사 구현 방법 : lodash 라이브러리의 cloneDeep메소드를 사용하여 Node.js에서 실행

```jsx
const _ = require("lodash");

const c2 = _.cloneDeep({ name: "property" });
```

6.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
function changeVal(primitive, person) {
  primitive += 100;
  person.name = "Kim";
}

var primitive = 100;
var person = { name: "Lee" };

console.log(primitive); // 100
console.log(person); // { name: 'Lee' }

changeVal(primitive, person);

// 원시 값은 원본이 훼손되지 않으므로 그대로 출력된다.
console.log(primitive); // 100
// 객체는 원본이 훼손된다.
console.log(person); // { name: 'Kim' }
```
