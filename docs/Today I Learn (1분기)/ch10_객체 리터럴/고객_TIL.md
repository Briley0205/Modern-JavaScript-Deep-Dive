## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.17

**오늘 읽은 범위**  10장 객체 리터럴

### 객체 리터럴 📑



---



### 객체란?
```
객체는 0개 이상의 프로퍼티로 구성된 집합이며, 프로퍼티는 key와 value로 구성된다.
```
---
### 프로퍼티
 프로퍼티를 나열할 때는 쉼표(,)로 구분한다.
 
 프로퍼티 키와 값으로 사용할 수 있는 값은 다음과 같다
 
 # 프로퍼티 키 : 빈 문자열을 포함하는 모든 문자열 또는 심벌값
 # 프로퍼티 값 : 자바스크립트에서 샤용할 수 있는 모든 값


## key

 키는 값에 접근할 수 있는 이름으로서 식별자 역할을 한다.
 
 식별자 네이밍 규칙을 준수하는 이름은 따온표를 생략할 수 있고
 식별자 네이밍 규칙을 준수하지 않는 이름은 반드시 따온표를 사용해야한다.
```javascript 
  var person = {
	firstName : 'Ung-mo',   // 식별자 네이밍 규칙을 준수하는 프로퍼티 키
    'last-name': 'Lee'    // 식별자 네이밍 규칙을 준수하지 않는 프로퍼티 키
}
```
# 1. key를 동적으로 생성

```js
var obj = {};
var key = 'hello';

var obj = {[key] : 'world'}
// obj[key] = 'world';  이렇게 해도 된다.

console.log(obj) //{ hello: 'world' }
```

# 2. key를 동적으로 생성
```js
var foo = {
  '' : '' // 빈 문자열 사용가능
};
console.log(foo); // {"": ""}

```
# 3. key는 암묵적 타입변환을 통해 문자열이 된다.
```js
var foo = {
0:1,
1:2,
2:3
}

console.log(foo); // {0: 1, 1: 2, 2: 3}
```

# 4. var, function과 같은 예약어를 key로 사용해도 에러가 발생하지 않는다.

하지만 예상치 못한 에러가 발생할 여지가 있으므로 권장하지 않는다.


# 5. key 중복

이미 존재하는 key를 중복 선언하면 나중에 선언한 프로퍼티가 먼저 선언한 프로퍼티를 덮어쓴다.

이때 에러는 발생하지 않는다.


```js
var foo = {
    name : 'Lee',
    name : 'Kim'
};

console.log(foo); // {name: "Kim"}
```

### 4. 메서드

메서드는 객체에 묶여 있는 함수를 의미한다. 

```js
var circle = {
    radius: 5, // <- 프로퍼티
    
    // 원의 지름
    getDiameter: function() { // <- 메서드
    	return 2 * this.radius; // this는 circle을 가리킨다.
      }
};

console.log(circle.getDiameter()); // 10
};

console.log(foo); // {name: "Kim"}
```

### 5. 프로퍼티 접근
프로퍼티에 접근하는 방법은 다음과 같이 두 가지다.

- 마침표 프로퍼티 접근자(.)를 사용하는 마침표 표기법
- 대괄호 프로퍼티 접근 연산자([...])를 사용하는 대괄호 표기법
 

key가 식별자 네이밍 규칙을 준수한 이름은 두 가지 방법 모두 사용가능하다.


```js
var person = {

	name : 'Lee'
};

//마침표 표기법에 의한 프로퍼티 접근
console.log(person.name); // Lee

// 대괄호 표기법에 의한 프로퍼티 접근
console.log(person['name']); // Lee
```
# 1) 대괄호 프로퍼티 접근 연산자 내부에 지정하는 프로퍼티 키는 반드시 따옴표로 감싼 문자열이어야 한다.
(따온표로 하지 않으면 자바스크립트 엔진은 식별자로 해석한다.)

```js
var person = {
    name: 'Lee'
};

console.log(person[name]); // ReferenceError: name is not defined
```


# 2) 객체에 존재하지 않는 프로퍼티에 접근하면 undefined를 반환한다. 
이때 에러가 발생하지 않는 다는 것에 주의하자

```js
var person = {
    name: 'Lee'
};

console.log(person.age); // undefined
```

# 3) key가 식별자 네이밍 규칙을 준수하지 않는 이름은 반드시 대괄호 표기법을 사용해야 한다. 
     (단, key가 숫자로 이뤄진 문자열인 경우 따온표를 생략할 수 있다.)
```js

var person = {
    'last-name' : 'Lee',
    1: 10
};

pserson.'last-name' ; // x
person.last-name; // x

person[last-name]; // last is not defined
person['last-name']; // Lee

// 프로퍼티 키가 숫자로 이뤄진 문자열인 경우 따온표를 생략할 수 있다. 

person.1; // x
person.'1'; // x
person[1]; // 10
person['1']; // 10

```
     
     
### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭


```
항상 객체를 적당히 알아서  코테 문제풀때마다  구글링을 했었는데 이번기회에 확실히 정리해서 좋았다. 
그래서 100% 안다고 할 수 없으니 여러번 봐야할 것 같다. 
다시 복습  키는 빈 문자열을 포함한는 모든 문자열 또는 심벌 값 (숫자를 적어도 암묵적 변환을 통해서 문자열로 변경된다.)
프로퍼티 값은 자바스크립트에서 사용할 수 있는 모든 값 
```

---

### 다른 분이 작성하신 TIL에 대한 소감
