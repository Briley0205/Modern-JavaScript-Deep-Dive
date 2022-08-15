## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.08

**오늘 읽은 범위** : 22장 this

### this 키워드의 동적 바인딩 📑

---

### this 키워드 바인딩

> this 바인딩은 함수 호출 방식에 의해 동적으로 결정된다.
```js
// 객체 리터럴 => 메서드를 호출한 객체, me를 가리킨다.
const me = {
    age: 21,
    getAge() {
        return this.age + 1;
    }
}
console.log(me.getAge());

// 생성자 함수 => 함수가 곧 생성할 인스턴스를 가리킨다.
function Me(age) {
    this.age = age;
}
Me.prototype.addAge = function() {
    return this.age + 1;
}
const me = new Me(21);
console.log(me.addAge()); // 22
```
또한 .addEventListener() 함수에 전달되는 함수 객체 내부에서는</br>
HTML element 그 자체를 가리킨다.
```js
const body = document.querySelector("body");
body.addEventListener("click", function() {
    console.log(this); // <body>...</body>
})
//.addEventListener() body 객체의 메서드로 정의되었으므로,
// .앞의 상수가 바인딩되어 HTMLelement를 가리키게 된 것이다. 
```
++ 브라우저 콘솔 전역에서는 window 전역 객체를 가리키기도 한다.
```js
console.log(this) // window {...}
```

### 함수 호출 방식에 따른 this 바인딩 🧵

`> 일반 함수 호출` : 전역 객체가 this에 바인딩된다.</br>
`> 메서드 호출` : 메서드를 호출할 때 .연산자 앞에 기술한 객체가 바인딩된다.</br>
`> 생성자 함수 호출` : 생성자 함수가 앞으로 생성할 인스턴스가 바인딩된다.</br>

---

### 다른 분이 작성하신 TIL에 대한 소감