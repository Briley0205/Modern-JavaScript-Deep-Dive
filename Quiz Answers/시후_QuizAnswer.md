### Quiz 

```js
/** 원본까지 다 합해서 400줄이 넘는 파일이므로 중략 */
```

6. 다음 코드의 출력을 예상하고 이유를 설명하라.

```javascript
function changeVal(primitive, person) {
    primitive += 100;
    person.name = 'Kim';
}

var primitive = 100;
var person = {name: 'Lee'};

console.log(primitive);
console.log(person);

changeVal(primitive, person);

console.log(primitive);
console.log(person);
```


#### 해설 및 풀이

1. 타입 변환과 단축 평가 문제 (p. 119 ~ 122)

> 논리 연산자는 논리 연산의 결과를 결정하는 피연산자의 값을 그대로 반환한다.
```js
console.log('Cat' && 'Dog'); // Dog
console.log('Cat' || 'Dog'); // Cat
```
> elem이 Falsy 값(null or undefined)이면 elem으로 평가되고 </br> Truthy값이라면 elem.value로 평가된다.
```js
var elem = null;
var value = elem && elem.value;
// value = null && undefined;
console.log(value); // null
value = elem?.value; // undefined;
console.log(value); // undefined;
```
> Falsy값 0 이나 ' '은 객체로 평가될 때도 있다.
```js
var str = '';
var length1 = str && str.length; // 공백
// length1 = '' && 0;
var length2 = str?.length; // 0
console.log(length1, length2); // 공백 0
```


2. '값에 의한 전달'과 '참조에 의한 전달' 설명 문제 (p. 142, 151) </br>
💡 북클럽을 준비하기 전, 글쓴이가 읽었던 질문을 토대로</br> 설명하도록 하겠다.</br>

💻 얼마 전, 'O'씨가 시험삼아 작성한 소스 코드이다.</br>
✅ 복사하여 전달했을 때, 원시 값과 객체 값의 결과가 다르다며,</br> 왜 이렇게 동작하는지 궁금하다고 가져왔다.

> 값에 의한 전달
```js
let a = '왜이래';
let b = a;
console.log(a, b) // '왜이래', '왜이래'

새로운 원시 값 '왜이래'가 생성되어 b에 할당된다.
(정확히는 메모리 주소를 전달한 후 메모리 공간에 접근하여 
값을 참조한다. 때문에 "공유에 의한 전달"이라고도 불린다.
이 (할당)시점에 두 변수가 기억하는 메모리 주소가 같을 수 있다.)

b = '이상해';
console.log(a, b) // '왜이래', '이상해'

하지만 a 변수와 b 변수의 값은 다른 메모리 공간에 저장된
값이므로, b에 새로운 원시 값을 할당시켜도 a 변수에는 
아무런 영향도 미치지 못한다.
```

> 참조에 의한 전달
```js
let arr = [1, 2, 3];
let arr2 = arr
console.log(arr === arr2); // false
console.log(arr, arr2); // [1, 2, 3], [1, 2, 3]

변수 arr가 기억하는 메모리 주소(참조 값)를 그대로 복사한다.
저장된 메모리 주소는 다르지만 동일한 참조 값을 갖는다.
때문에 두 개의 식별자가 하나의 객체를 공유하게 된다. 

arr2.push(4);
console.log(arr, arr2); // [1, 2, 3, 4], [1, 2, 3, 4]

따라서 원본 또는 사본 중 어느 한쪽에서 객체를 변경하면 
서로 영향을 주고받는다.
```

3. 원시 값과 객체의 비교 챕터 문제 (p. 153)
```javascript
var person1 = {
    name: 'Lee',
}

var person2 = {
    name: 'Lee',
}

console.log(person1 === person2); // 1 false
console.log(person1.name === person2.name); // 2 true

두 변수가 가리키는 내용은 비록 동일하지만 다른 메모리에 
저장된 별개의 객체이므로 1은 false이다.
하지만 프로퍼티 값을 참조하면, 표현식이 된다.
두 표현식 모두 'Lee'로 표현되므로, 2는 true다.

person1 = person2;
console.log(person1 === person2); // true

더하여, person1에 person2의 참조값을 할당하면
두 변수가 기억하는 참조값이 동일해 지므로
true를 반환한다.
```

4. 프로퍼티의 동적 생성 및 함수표현식 문제
```javascript
var a = {};
var func = function(b) {
  b = (b.a=1);
  b.b = 2; // 무시
} // 함수 리터럴 표현식
func(a); 
a의 참조 값을 복사하여 함수표현식의 매개변수로 전달한다.

console.log(a); // {a: 1}
a 변수와 func 함수표현식 변수가 같은 메모리를 공유하게 되므로,
함수표현식에서 동적으로 프로퍼티를 생성했을 때,
a 전역변수에 영향을 미친다.
```

5. 얕은 복사와 깊은 복사 문제 (p. 150)

✔ 얕은 복사란 ?</br>

**객체의 경우** : 1 Depth 까지만 복사

**객체 값의 경우** : 메모리에 참조 값을 복사하여 전달하는 것

✔ 깊은 복사란 ?</br>

**객체의 경우** : 2 Depth 객체에 중첩되어 있는 객체까지 복사

**원시 값의 경우** : 메모리에 새로운 원시 값을 생성하여 전달하는 것

```js
const intro = {name: '시후' {age: 21}};

// 얕은 복사
const clone1 = {...intro};
console.log(intro === clone1); // false
console.log(intro.name === intro2.name) // false

// 깊은 복사
const deep = require('lodash');
const clone2 = deep.cloneDeep(intro);
console.log(intro === clone2) // false
console.log(intro.name === clone2.name) // true
```

6. 참조에 의한 전달과 외부 상태의 변경 문제 (p. 175)
```javascript
function changeVal(primitive, person) {
    primitive += 100; // 변경 불가
    person.name = 'Kim';
}

var primitive = 100;
var person = {name: 'Lee'};

// 함수 실행 전
console.log(primitive); // 100
console.log(person); // {name: 'Lee'}

changeVal(primitive, person);
// changeVal(원시 값, 객체 값);

console.log(primitive); // 100 --> 원본 훼손 X
console.log(person); // {name: 'Kim'} --> 내용물이 바뀜
```
함수 내 매개변수에서 원시 값을 직접 변경할 수 없기 때문에</br>
할당된 원시 값을 새로운 원시 값으로 변경했다</br>
객체 타입 인수는 변경 가능한 값 이므로 직접 변경할 수 있다.</br> 때문에 재할당 없이 직접 할당된 객체를 변경했다.