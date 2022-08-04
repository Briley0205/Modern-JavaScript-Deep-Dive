# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.08.03 -. 04

**오늘 읽은 범위** : <br>
17장, 생성자 함수에 의한 객체 생성

<br>

## ✨**17장-생성자 함수에 의한 객체 생성**✨

### ➡️Object 생성자 함수

new 연산자와 함께 Object 생성자 함수를 호출시 빈 객체를 생성하여 반환한다. 빈 객체 생성 이후 프로퍼티 또는 메서드를 추가해서 객체를 완성할 수 있다.

```js
//빈 객체 생성
const player = new Object();

//프로퍼티 추가
player.job = "farmer";
player.sayJob = function () {
  console.log(`Hello, my job is ${this.job}`);
};

console.log(player); // {job:"farmer", sayJob:f}
player.sayJob(); //Hello, my job is farmer
```

특별한 이유가 없다면 Object 생성자 함수를 꼭 써야만 하는 건 아니다. 경우에 따라 다른 방식이 더 유용할 수도 있다.

<br>

❕생성자 함수란 ? <br>
new 연산자와 함께 호출하여 객체를 생성하는 함수

❕인스턴스 <br>
생성자 함수에 의해 생성된 객체

### ➡️생성자 함수

동일한 프로퍼티를 가진 객체를 여러 개, 많이 만들어야 한다면 객체 리터럴로 생성하는 건 비효율적인 일이다.
이러한 비효율성을 낮추고 더 간편하게 작업하기 위해 **생성자 함수**를 쓴다.

```js
function Player(name) {
  //생성자 함수 내부 this는 생성자 함수가 생성할 인스턴스를 가리킨다
  this.name = name;
  this.getName = function () {
    return `Hello my name is ${this.name}`;
  };
}

//인스턴스 생성
const player1 = new Player("grace");
//플레이어 이름이 grace인 객체 생성
const player2 = new Player("maria");
//플레이어 이름이 maria인 객체 생성

console.log(player1.getName()); //My name is grace
console.log(player2.getName()); //My name is maria
```

new연산자와 함께 호출시 해당 함수는 생성자 함수로 동작한다. 만일 new연산자 없이 생성자 함수를 호출시 일반 함수로 동작한다.

 <br>

### ➡️생성자 함수 인스턴스 생성 과정

1.인스턴스 생성 및 this 바인딩

```js
function Player(name) {
  console.log(this); // Player{}

  this.name = name;
  this.getName = function () {
    return `Hello my name is ${this.name}`;
  };
}

//인스턴스 생성
const player1 = new Player("grace");
```

:암묵적으로 빈 객체가 생성된다. 이때 완성되지 않은 빈 객체가 인스턴스다. 이 인스턴스는 this에 바인딩된다. 이 프로세스는 런타임 이전에 실행된다.

2.인스턴스 초기화

```js
function Player(name) {
  //1.암묵적으로 인스턴스가 생성됨 + this에 바인딩됨

  //2.this에 바인딩된 인스턴스를 초기화
  this.name = name;
  this.getName = function () {
    return `Hello my name is ${this.name}`;
  };
}

//인스턴스 생성
const player1 = new Player("grace");
```

생성자 함수 내 기술된 코드가 한 줄씩 실행되어 this에 바인딩되어 있는 인스턴스를 초기화한다.

3.인스턴스 반환

```js
function Player(name) {
  //1.암묵적으로 인스턴스가 생성됨 + this에 바인딩됨

  //2.this에 바인딩된 인스턴스를 초기화
  this.name = name;
  this.getName = function () {
    return `Hello my name is ${this.name}`;
  };
  //3.완성된 인스턴스가 바인됭된 this가 암묵적으로 반환된다
}

//인스턴스 생성, Player생성자 함수는 this를 반환한다.
const player1 = new Player("grace");
```

생성자 함수 내부 모든 프로세스가 끝난 후 완성된 인스턴스가 바인딩된 this가 반환된다. <br>
➕this가 아닌 다른 객체를 반환하려고 하면 this가 아닌 return문에 명시된 객체가 반환된다. <br>
➕원시 값을 반환시 원시 값 반환은 무시되고 this가 반환된다.

❕따라서 생성자 함수 내부에서는 return문을 생략하자.

<br>

### ➡️내부 메서드 [[Call]], [[Construct]]

함수가 일반 함수로 호출되면 함수 객체 내부 메서드인 [[Call]]이 호출되고 new 연산자와 함께 생성자 함수로 호출시에는 [[Construct]]가 호출된다.

함수 객체는 반드시 callable, 즉 호출할 수 있어야 하기에 모든 함수는 내부 메서드 [[Call]]을 갖고 있다.
반면 모든 함수가 [[Construct]]j를 갖는 건 아니다.

❕결론적으로 함수 객체는 callable이면서 contructor이거나, callable이면서 non-constructor다.

<br>

### ➡️constructor, non-constructor 구분

constructor :
함수 선언문, 함수 표현식, 클래스

non-constructor :
메서드(ES6 축약 표현), 화살표 함수

즉 함수 정의 방식에 따라 구분한다.

### ➡️new.target

this와 유사하게 constructor인 모든 함수에서 지역 변수와 같이 사용되며 메타 프로퍼티라고도 한다.

new연산자와 함께 생성자 함수로서 호출되면 함수 내부 new.target은 함수 자신을 가리킨다. (new 연산자 없이 일반 함수로서 호출된 함수 내부 new.target은 undefined)

<br>

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
바인딩 :
식별자와 값을 연결하는 과정.
예)변수 선언은 변수 이름(식별자)과 확보된 메모리 공간의 주소를 바인딩한다고 말한다.

```

<br>

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
이전에 작업한 JS 중 같은 프로세스를 가진 함수를 여러 개 하나하나 써서 작업한 적이 있었는데, 그때도 비효율적이라는 생각을 했었다. 생성자 함수가 있다면 일일이 붕어빵 하나하나 다 만들어야 하는 게 아니라, 붕어빵 틀이 있어서 반죽과 팥만 있으면 더 쉽게 만들 수 있는 것이다. 가능한 대로 이전에 작업했던 코드를 더 간단하게 손볼 수 있겠다.
```
