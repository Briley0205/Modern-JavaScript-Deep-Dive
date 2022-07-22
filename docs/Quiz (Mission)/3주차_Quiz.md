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
