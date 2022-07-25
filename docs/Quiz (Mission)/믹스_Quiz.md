### Quiz 


1.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
console.log('Cat' && 'Dog');
console.log('Cat' || 'Dog');

var elem = null;
var value = elem && elem.value;
console.log(value);
value = elem?.value;
console.log(value);

var str = '';
var length1 = str && str.length;
var length2 = str?.length;
console.log(length1, length2);
``` 

2."값에 의한 전달"와 "참조에 의한 전달"을 설명하고, 자바스크립트의 전달 방법을 기술하라.


3.아래 코드의 결과를 예상하고 이유를 설명하라.

```javascript
var person1 = {
    name: 'Lee',
}

var person2 = {
    name: 'Lee',
}

console.log(person1 === person2);
console.log(person1.name === person2.name);

person1 = person2;
console.log(person1 === person2);
```

4.다음 코드의 출력를 예상하고 이유를 설명하라.

```javascript
var a = {};
var func = function(b) {
  b = (b.a=1);
  b.b = 2;
}
func(a);
console.log(a); 
```

5."얕은 복사"와 "깊은 복사"를 설명하고, 자바스크립트에서 깊은 복사를 구현하는 방법을 설명하라.(라이브러리 사용)

6.다음 코드의 출력를 예상하고 이유를 설명하라.

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

자유롭게 풀이해주세요! 

#### 1번 풀이
```javascript
console.log('Cat' && 'Dog'); // Dog
console.log('Cat' || 'Dog'); // Cat
// 위의 두 문장은 논리 연산자를 사용한 단축 평가로 각각 Dog와 Cat을 반환한다.
// && 연산자는 두 피연산자 모두 true여야 하므로 결과를 확정하는 두번째 피연산자 Dog를 그대로 반환한다.
// || 연산자는 둘 중 하나만 true라면 true이므로 Truthy값인 첫번째 피연산자 Cat에서 반환이 이루어진다.

var elem = null;
var value = elem && elem.value;
console.log(value); //null
//객체가 가르키기를 기대하는 변수가 null 또는 undefined인지 단축평가를 통해 확인해볼 수 있는 유용한 방법으로 좌항 피연산자가 false로 평가되는 값(undefined,null,Nan 등)이면 좌항 피연산자를 그대로 반환한다.
value = elem?.value;
console.log(value);//undefined
//옵셔널 체이닝 연산자는 좌항의 피연산자가 null 또는 undefined인 경우 undefined을 반환하고 그렇지 않으면 우항의 프로퍼티 참조를 이어간다.

var str = '';
var length1 = str && str.length;
var length2 = str?.length;
console.log(length1, length2);// '', 0
//위의 해설과 이어서, &&의 경우 length참조를 할수가 없지만 ?.의 경우 우항의 프로퍼티 참조를 이어가기 때문에 length의 참조가 가능하다.
``` 

#### 2번 풀이
"값에 의한 전달"와 "참조에 의한 전달"을 설명하고, 자바스크립트의 전달 방법을 기술하라.<br>

    변수에 변수를 할당할 경우 할당하는 변수의 원시 값이 복사되어 전달이 되는데, 이를 값에 의한 전달이라 한다. 즉 두가지는 다른 메모리 공간에 저장된 별개의 값이며 서로 간섭할 수 없다. (실질적으로는 메모리 주소를 전달하는 것)
    
    객체를 가리키는 변수를 다른 변수에 할당하면 원본의 참조 값이 복사되어 전달된다. 이를 참조에 의한 전달이라 한다. 두 변수의 저장된 메모리 주소는 다르지만 동일한 참조 값을 가진다. 즉 두개의 식별자가 하나의 객체를 공유하는 것이며, 원본 또는 사본 중 어느 한쪽에서 객체를 변경하면 서로 영향을 주고 받는다.


#### 3번 풀이
```javascript
var person1 = {
    name: 'Lee',
}

var person2 = {
    name: 'Lee',
}

console.log(person1 === person2); // false
// person1과 person2는 각각 다른 메모리에 저장된 객체이다. 그렇기 때문에 일치비교연산자로 비교했을때, 둘은 동일하지 않다.
console.log(person1.name === person2.name); //true
// 프로퍼티값을 참조하여 비교하는 이 문장은 값으로 평가될수 있는 두 표현식의 비교임으로 원시값을 가지고 평가된다. 따라서 동일하게 "Lee"값을 반환하고 결과는 true가 나오게된다.

person1 = person2;
console.log(person1 === person2); //true
//참조에 의한 전달로, person1 = person2;에서 둘은 동일한 참조 값을 가지게 된다. 즉 person1 === person2에서 동일한 객체를 참조하므로 결과값은 true이다.
```

#### 4번 풀이

```javascript
var a = {};
var func = function(b) {
  b = (b.a=1);
  b.b = 2;
}
func(a);
console.log(a); // {a : 1}
//func(a)로 함수 호출 시, 함수 내부의 b = (b.a=1)를 통해 프로퍼티가 동적으로 생성되어 a에 a : 1이라는 프로퍼티가 생성된다.
```

#### 5번 풀이
"얕은 복사"와 "깊은 복사"를 설명하고, 자바스크립트에서 깊은 복사를 구현하는 방법을 설명하라.(라이브러리 사용)

    얕은 복사 - 참조 값을 복사 (한 단계만 복사)
    깊은 복사 - 원시 값처럼 완전한 복사본
    자바스크립트에서는 node.js에서 lodash의 cloneDeep을 통해 깊은 복사를 구현한다.


#### 6번 풀이

```javascript
function changeVal(primitive, person) {
    primitive += 100;
    person.name = 'Kim';
}

var primitive = 100;
var person = {name: 'Lee'};

console.log(primitive); //100
console.log(person); //{name: 'Lee'}
//각 변수의 값이 그대로 반환

changeVal(primitive, person);

console.log(primitive); //100
//원시값은 영향을 받지 않는다.
console.log(person); //{name: 'Kim'}
//함수가 호출되면서 person.name = 'Kim'으로 변경되는 부수 효과가 발생, 객체 타입 인수는 변경이 가능한 값이기 때문에 재할당되지 않고 할당된 객체가 변경된다.
```
