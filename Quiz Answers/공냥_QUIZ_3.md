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

```javascript
1번 문제
console.log('Cat' && 'Dog');
//Dog
논리곱 연산자는 좌항에서 우항으로 평가가 진행된다. 먼저 평가가 된 Cat은 true로 평가되지만 이 시점에서 표현식은 아직 평가될 수 없다. 두 번째 피연산자인 Dog도 평가해야하며 이는 즉  표현식 결과 결과로 결정된다. 때문에 Dog를 반환한다.

console.log('Cat' || 'Dog');
//Cat
논리합 연산자는 Cat과 Dog 중 하나만 true로 평가되어도 true를 반환된다. 마찬가지로 좌항에서 우항으로 평가가 진행된다. Cat이 true인 시점에서 Dog를 평가하지 않아도 표현식 평가가 가능하다. 고로 Cat을 반환한다.

var elem = null;
var value = elem && elem.value;
console.log(value);
//null
//elem이 거짓(null, undefined 등)이면 elem으로 평가되고, 참이면 elem.value로 평가된다. elem은 null이므로 falsy 값이기에 elem으로 평가된다. 즉 elem의 값인 null이 로그에 출력된다.
value = elem?.value;
console.log(value);
//undefined
//elem이 null 또는 undefined인 경우 undefined를 반환, 그게 아니라면 우항의 프로퍼티 참조를 이어가게 되는데 여기에서 elem은 null이므로 undefined를 반 환한다. 즉 undefined가 로그에 출력된다.

var str = '';
var length1 = str && str.length;
var length2 = str?.length;
console.log(length1, length2);
//undefined, 0
//str의 값이 falshy면 str을, truthy면 str.length를 반환한다. str은 falsy이므로 str을 반환한다. str은 undefined이므로 변수 length1은 undefined 값을 가지고 있다.
//length2에서는 str이 undefined이거나 null이 아니면 우항 프로퍼티 참조를 이어가게 된다. str은 null도 undefined도 아니므로 우항 프로퍼티 length를 참조하게 된다. 즉 0이 나온다.
```

2번 문제

```
값에 의한 전달 :
원시 타입 값을 갖는 변수를 타 변수에 할당시 원래의 원시 값이 복사되어 전달이 된다. 이 전달 방식을 값에 의한 전달이라고 한다.

참조에 의한 전달 :
객체를 가리키는 변수(객체 데이터가 담긴 주소를 가리키는)를 타 변수에 할당시 원본이 아닌 원본의 참조 값이 복사되는 방식을 참조에 의한 전달이라 한다.

자바스크립트는 변수에 저장된 값, 즉 식별자가 가지고 있는 메모리 공간에 저장된 값을 복사해서 전달한다.
```

3번 문제

```javascript
var person1 = {
  name: "Lee",
};

var person2 = {
  name: "Lee",
};

console.log(person1 === person2);
//false
//person1과 person2라는 각 메모리 주소에 있는 객체 내용은 같지만 각자 다른 메모리에 저장된 별개의 객체라 할 수 있다. 메모리 주소가 다른 것이다. 때문에 false이다.
console.log(person1.name === person2.name);
//true
//person1과 person2은 둘 다 'Lee'로 평가된다. 즉 true다.

person1 = person2;
console.log(person1 === person2);
//true
// 깊은 복사를 하게 되며 완전한 복사본이 만들어짐. 때문에 콘솔 로그시 둘은 값이나 값의 타입 모두 다 일치하므로 true를 출력한다.
```

4번 문제

```javascript
var a = {}; // a의 값은 object
var func = function (b) {
  b = b.a = 1;
  b.b = 2;
}; // f
func(a); // 함수 호출 단계. 생성자 함수의 인수의 a를 파라미터로 전달.
//파라미터인 b는 인수 a를 받아들이게 되고 함수 내부에서 a를 가지고 함수 실행을 한다. b = (b.a = 1) 줄에서는 a = {a : 1};밑줄의 재할당으로 b.b 그러니까 a.a는 2가 된다.
console.log(a);
//때문에 a를 콘솔 로그하면 {a : 1} 이라는 값이 출력된다.

//*이 부분은 많이 헷갈리네요... 다른 분들의 답과 풀이가 절실히 궁금합니다.
```

5번 문제

```javascript
//깊은 복사는 '실제 값'을 새로운 메모리 공간에 복사하는 것을 의미하며,얕은 복사는 '주소 값'을 복사한다는 의미이다.

//즉 얕은 복사는
//객체를 할당한 변수를 다른 변수에 할당하는 것이기도 하며
let x = 1;
let copyX = x;
console.log(copyX === x); //true

//깊은 복사는
//원시 값을 할당한 변수를 다른 변수에 할당하는 것이기도 하다.
let x1 = { a: 1 };
let copyX1 = x1;
console.log(copyX1 === X1); //true
```

6번 문제

```javascript
function changeVal(primitive, person) {
  primitive += 100;
  person.name = "Kim";
}

var primitive = 100;
var person = { name: "Lee" };

console.log(primitive); // 100
console.log(person); // {name : 'Lee'}

changeVal(primitive, person);
//원시값은 값 자체가 복사되고, 객체는 참조 값이 복사되어 전달이 된다.
//때문에 기존 primitive는 변경이 되지 않는다. 때문에 값이 그대로다.
//반면 객체는 참조값을 복사한 것이므로 함수에서 변경할 경우 적용이 된다. 때문에 person의 객체 데이터에 변경이 일어난다.
console.log(primitive); // 100
console.log(person); // {name : 'Kim'}
```
