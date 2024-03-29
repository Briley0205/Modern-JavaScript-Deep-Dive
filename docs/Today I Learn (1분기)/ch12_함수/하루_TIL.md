## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.23

**오늘 읽은 범위** : 12장 함수


### 함수
+ 함수는 일련의 과정을 문으로 구현하고 코드 블록으로 감싸서 하나의 실행 단위로 '정의'한 것 (변수는 선언이라 하고 함수는 정의라 한다.)
+ 전달 받는 변수를 __매개변수(parameter)__, 입력을 __인수(argument)__, 출력을 __반환값(return value)___ 이라 한다.
+ 함수를 실행하기 위해선 인수를 매개변수로써 전달하며, 함수의 실행을 명시적으로 지시해야한다. 이를 __함수 호출__ 이라 한다.
#### 사용의 이유
+ 중복되는 코드를 여러번 작성하는 것을 대신해, 함수를 정의하고 몇번이고 호출할 수 있다. __코드를 재사용__ 할 수 있기에 생산성을 올려준다. 
+ 재사용을 높여주는 함수는 유지보수의 편의성과 신뢰를 높여주는 효과가 있다.
#### 함수 리터럴 
+ 함수 리터럴은 function 키워드, 함수 이름, 매개변수 목록, 함수 몸체 로 구성된다.
+ 리터럴은 값을 생성하기 위한 표기법이며 함수 리터럴 또한 평가되어 값을 생산한다. 이 값은 객체이며, 즉, __함수는 객체다.__
---

</br>

### 함수 정의
+ 함수 정의란 함수를 호출하기 이전에 인수를 전달받을 매개변수와 실행할 문들, 그리고 반환할 값을 지정하는 것을 말한다.(정의된 함수는 함수 객체가 된다.)
+ 함수 리터럴에서 함수 이름은 함수 몸체 내에서만 참조할 수 있는 식별자다. 즉, 외부에서는 함수를 참조할 수 없다.
+ {} 는 중의적 표현이다 문맥에 따라 블록문으로 해석될 수도 객체 리터럴로 해석될 수도 있다. (값으로 평가되면 객체 리터럴)

##### 함수 선언문
```
function add(x, y) {
  return x+y;
}
// 함수 이름은 함수 몸체 내에서만 참조할 수 있는 식별자임으로 원래라면 add(1, 2) 와 같이 호출할 수 없어야한다.
// 그러나 자바스크립트 엔진에서만 함수 선언문에서의 함수 객체를 가르키고 함수 이름과 같은 식별자를 암묵적으로 생성해주기에 가능하다.
```

</br>

#### 함수 표현식
```
var add = function(x, y) {
  return x+y;
}
```
+ 값의 성질을 갖는 객체를 일급 객체라 한다. 자바스크립트 함수는 일급 객체이다. 그리고 이러한 함수 정의 방식을 함수 표현식이라 한다.
+ 함수 선언문은 표현식이 아닌 문이고 함수 표현식은 표현식인 문이다.   
   + 함수 선언문과 표현식은 정의한 함수의 생성 시점이 다르다. 함수 선언문은 함수 호이스팅의 특징을 가지지만 표현식은 그렇지 않다.

</br>

#### arrow function (ES6)
+ 항상 익명 함수로 정의 한다.
```
var add = (x, y) => x+y;
```

</br>

#### 함수 호출
+ 매개변수는 함수를 정의할 때 선언하며, 함수 몸체 내부에서 변수와 동일하게 취급된다.
   + 함수 호출 시 함수 몸체 내에서 매개변수가 생성되고 undefined 로 초기화 이후 인수가 할당됨
+ 이상적인 함수는 한 가지 일만 해야 하며 가급적 작게 만들어야 한다. 
   + 이상적인 매개변수 개수는 0개이고 3개 이상을 넘지 않도록 주의한다. (최대 개수에 제한이 없음) 
+ 원시 값과 객체의 비교와 같이 매개변수 값에 따라 값에 의한 호출, 참조에 의한 호출로 구별될 수 있으며 방식이 동일함.
```
function changeVal(primitive, person) {
    primitive += 100;
    person.name = 'Kim';
}

var primitive = 100;
var person = {name: 'Lee'};

console.log(primitive);
console.log(person); 

changeVal(primitive, person);

console.log(primitive); // 100
console.log(person); // {name: 'Kim'}
// 원시 값은 수정될 수 없으나, 객체는 수정 가능함
```




---

</br>


