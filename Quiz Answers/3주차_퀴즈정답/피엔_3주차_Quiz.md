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

1. 
console.log('Dog')
console.log('Cat')이 출력된다.
&&연산자의 경우 두개의 true값이 들어가면 두번째 값을 가지고 있는 상태에서 true값이 두개 들어가 결과가 나오기 때문에 'Dog'값을 출력하고, ||연산자의 경우 true값이 한개 들어온 순간 값을 반환하기 때문에 처음 true값이 들어온 상태의 값 'Cat'을 출력한다.

console.log('null');
console.log('undifined')가 출력된다.
elem && elem.value 에서 elem값이 null로 falsy값이라 좌항 피연산자를 그대로 출력하여 elem의 값인 null이 출력된다.
두번째 콘솔 출력은 옵셔널 체이닝 연산자로 변수가 null이나 undefined 값이면 undefined를 반환한다. elem의 값은 null이기에 최종적으로 undefined를 출력한다.

console.log('', 0 )을 출력한다
length1 변수의 경우 str은 '' 값을 가지고 있고 str.length는 0 의 값을 가지고 있다 둘다 Falsy 값으로 str값을 반환해 length는 ''값을 가진다.
length2 변수의 경우 옵셔널 체이닝 연산자는 변수값이 null이나 undefined의 경우에만 undefined를 반환하고 그 외의 경우에는 우항의 프로퍼티를 참조하여 0값이 나오게 된다.
---

2.
자바스크립트의 변수는 데이터값을 기억하는게 아니라 데이터의 위치를 기억한다. 값에 의한 전달은 데이터의 위치에 있는 값을 다른 곳에 저장하여 그 위치를 기억한다.
그래서 값에 의한 전달을 한 경우 처음 변수를 변경 하거나 전달 된 변수를 변경 해도 서로 영향을 끼치지 않는다.
객체의 경우 데이터 위치를 참조하는 값을 기억한다. 객체 변수를 전달 할경우 객체를 저장해서 전달하는게 아니라 객체 참조값을 전달한다. 그래서 처음 나중에 전달 받은 값을 변경 하면 같은 값을 참조 하고 있기 때문에 값이 같이 바뀌게 된다.
---

3.
console.log(false)
console.log(true)
console.log(true)가 출력된다.
객체의 경우 같은 값을 담고 있더라도 서로 참조 하고 있는 객체가 다르기 때문에 person1 과 person2는 서로 다른 객체다 그리하여 false가 출력된다.
person1.name 과 person2.name의 경우 서로 원시값으로 평가 되어 결과 적으로 같은 단어이다. 그리하여 true가 출력된다.
세번째 console의 경우 그전에 person1 = person2를 선언해 두 변수 모두 같은 객체를 참조하게 되어 같은 값일 가지게 되었다 그리하여 true가 출력된다.
---

4.
a:1이 출력된다.
객체값은 참조가능한 값이라 함수에서 실행되어 변경 된값도 같이 변경 된다.
func(a)로 함수를 호출하여 함수 내부를 살펴보면 
b = (a.a=1);
b.b = 2; 라고 볼 수 있다. 함수 내부에 a.a=1을 실행시키면 a 객체에 a:1이 들어가고 b변수에 할당된다. 이때 b는 a가 아닌 다른값을 가르키고 있기때문에 두번째줄 b.b는 a객체에 영향을 끼치지 못한다. 그리하여 콘솔엔 a:1이 출력된다.
---

5.
기존에 객체는 새로 변수를 지정하더라도 참조값이 같아 하나를 수정해도 같이 수정되는 단점이 있었다. 얕은 복사와 깊은 복사는 원본과 다른 객체를 만들어 새로 참조값을 메모리 공간에 할당해 기존의 참조값과 다르다.
얕은 복사의 경우 처음 객체값을 복사해 다른 객체 참조값을 만들지만 중첩되어있는 객체값은 기존 참조값을 따라간다.
깊은복사는 얕은 복사와 달리 중첩되어 있는 모든 객체를 모두 참조값을 새로 복사해 모든 객체가 기존과 다른값을 참조하게 된다.
---

6.
console.log(100)
console.log({name: 'Lee'})

console.log(100)
console.log({name: 'Kim'})이 출력된다
처음 콘솔 출력 전까지 변수 선언후 별다른 값 변경이 없어 해당 콘솔 출력은 100, {name: 'Lee'}가 그대로 출력된다.
그 뒤 콘솔 출력전 changeVal(primitive,person)함수가 실행되었는데 함수 내부에서 primitive값은 100이 증가하였고 person.name 값은 'Kim' 으로 변경되 었다.
하지만 함수 내부의 값은 지역변수기 때문에 전역변수의 값을 변경 하지못한다. 그렇기에 함수 내부에선 primitive의 값은 100이 증가하였으나 함수외부의 primitive값은 100으로 변동이 없다.
하지만 person.name 값의 경우 person 변수의 경우 객체 참조값을 지정하고 있는 상태라 함수 내부에서 변경된 값이 변경되게 된다. 그리하여 person.name의 값은 함수를 벗어나도 'Kim'으로 변경된 상태이다.
그래서 함수가 실행되고 난 콘솔에는 바뀌지않는 100과 name:'Kim'이 출력된다.
