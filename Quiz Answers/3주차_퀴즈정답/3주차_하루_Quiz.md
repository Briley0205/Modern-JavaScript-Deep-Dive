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
```
1.
console.log('Cat' && 'Dog'); // True 이 출력된다 && 는 and 로 둘 다 충족 true 여야하며 마지막 값을 반환한다.
console.log('Cat' || 'Dog'); // Cat 이 출력된다. || 는 or 로서 첫번 째만 true 면 바로 값을 반환하고 Dog 는 읽지 않는다.

var elem = null;
var value = elem && elem.value;
console.log(value); // undefined 를 출력한다. null 또는 undefined 라면 undefined 를 반환한다.
value = elem?.value;
console.log(value); undefined 를 출력한다. null 또는 undefined 라면 undefined 를 반환한다.

var str = ''; // undefined 다.
var length1 = str && str.length;
var length2 = str?.length;
console.log(length1, length2); // undefined 는 string type 이 아님으로 length 속성을 사용할 수 없다.
```

```
2.
✔ 값에 의한 전달 
 변수에 원시 값을 갖는 변수를 할당하면 할당되는변수의 원시 값이 복사되어 전달된다.
  - 엄격히 표현하면 값이 아닌 메모리 주소가 전달된다.
 
✔ 참조에 의한 전달
 참조 값은 생성된 객체가 저장된 메모리 공간의 주소, 그 자체다.
 참조에 의한 전달은 객체를 가리키는 변수를 다른 변수에 할당하면 원본의 참조 값이 복사되어 전달 되는 것을 말한다.
 객체를 가리키는 원본 변수와 할당한 새로운 변수는 같은 객체를 가르킨다. 즉, 두 개의 식별자가 하나의 객체를 공유한다.
```

```
3.
var person1 = {
    name: 'Lee',
}

var person2 = {
    name: 'Lee',
}

console.log(person1 === person2); // false 내용은 같지만 다른 메모리 주소에 저장된 다른 객체다.
console.log(person1.name === person2.name); // true 다른 객체지만 원시 값을 비교하는 것임으로 일치한다.

person1 = person2;
console.log(person1 === person2);
```

```
4.
var a = {};
var func = function(b) {
  b = (b.a=1);
  b.b = 2;
}
func(a); // 무엇을 return 하는 것인지 이해를 잘 하지 못함
console.log(a); // undefined 를 출력한다.
```

```
5.
얕은 복사는 참조 값을 복사하고 깊은 복사는 객체에 중첩되어 있는 객체까지 모두 복사하여 원시 값과 같이 복사본을 만든다.
(위 값에 의한 전달 vs 참조에 의한 전달 개념 참고)
```

```
6.
function changeVal(primitive, person) {
    primitive += 100;
    person.name = 'Kim';
}
// 함수 선언문임으로 표현식이 아닌 값임과 동시에 호이스팅 특징을 가진다.

var primitive = 100;
var person = {name: 'Lee'};

console.log(primitive); // 100
console.log(person); // {name: 'Lee'}

changeVal(primitive, person);
// 함수 호출

console.log(primitive); // 100 원시 값은 원본이 훼손되지 않는다.
console.log(person); // {name: 'Kim'} 객체는 원본이 훼손된다.
```


