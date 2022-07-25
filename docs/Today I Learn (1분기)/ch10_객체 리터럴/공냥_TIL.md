## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : 2022.07.19

**오늘 읽은 범위** : 10장, 객체 리터럴

### ✨**뗄레야 뗄 수 없는 객체와 함수, 그리고 객체 리터럴**✨

➡️**객체란?** <br> -자바스크립트는 객체 기반 프로그래밍 언어다.<br> -객체는 변경 가능한 값이다. <br> -객체는 0개 이상의 프로퍼티와 메서드로 구성된 집합체다. <br>
여기에서 프로퍼티와 메서드란?

- 프로퍼티 : 객체의 상태를 나타내는 값 (data)
- 메서드 : 프로퍼티를 참조하고 조작할 수 있는 동작

❕객체는 **상태와 동작을 하나의 단위로 구조화**할 수 있다.❕

<br>

➡️**객체 생성법** <br>
자바스크립트는 **프로토타입 기반 객체지향 언어**로서 다양한 객체 생성 방법을 지원한다. <br>

- 객체 리터럴
- object 생성자 함수
- 생성자 함수
- object.create 메서드
- 클래스(ES6)

이중에서 일반적이며 간단한 방법은 **객체 리터럴**로 객체를 생성하는 것이다.

```javascript
let newObject = {};
console.log(typeof newObject);
//object

let player = {
  name: "tom", //프로퍼티
  level: 10, //프로퍼티
  defaultMotion: function () {
    console.log("do defaultMotion");
  }, //메서드
};
```

➡️**프로퍼티** <br>
프로퍼티는 **키key**와 **값value**로 구성된다.<br>
프로퍼티 키:빈 문자열 포함하는 모든 문자열 또는 심벌 값 사용 가능.<br>
프로퍼티 값 : 자바스크립트에서 쓸 수 있는 모든 값 <br>
➕프로퍼티 키를 사용할 때 식별자 네이밍 규칙을 따르지 않은 이름은 반드시 따옴표를 써줘야 한다. <br>

```javascript
let newPerson = {
  firstName: "영희",
  "last-name": "박",
};

console.log(newPerson);
//{firstName: "영희", last-name: '박'}
```

프로퍼티 키 `last-name`에 따옴표를 감싸지 않고 사용할 경우 `- 연산자`가 있는 표현식으로 해석한다.

```javascript
let newPerson = {
    firstName : '영희',
    last-name : '박'
};

console.log(newPerson);
//이 경우 syntaxError가 발생한다. Unexpected token...
```

➡️**메서드** <br>
자바스크립트의 함수 또한 객체이기에 값으로 취급할 수 있어서 프로퍼티 값으로도 사용할 수 있다. 프로퍼티 값이 함수인 경우 일반 함수와 구분 짓기 위해 **메서드**라고 부른다. 즉, 객체에 묶인 함수를 의미한다.

```javascript
let newPlayer = {
  level: 50,
  job: "healer",

  printLevel: function () {
    return this.level;
  }, //메서드
};

newPlayer.printLevel();
```

➡️**프로퍼티 접근** <br>
프로퍼티 접근 방법에는 두 가지가 있다.

1. 마침표 표기법
2. 대괄호 표기법

```javascript
let newPlayer = {
  level: 50,
  job: "healer",
};

console.log(newPlayer.level); // 50
console.log(newPlayer["level"]); // 50
```

대괄호 표기법 사용할 경우, 접근하고자 하는 프로퍼티 키는 **반드시 따옴표로 감싼 문자열**이어야 한다.
<br>

➡️**프로퍼티 값 갱신, 동적 생성, 삭제** <br>

```javascript
//프로퍼티 값 갱신
let newPlayer = {
  level: 50,
};

newPlayer.level = 30;
console.log(newPlayer); // {level: 30;}

//프로퍼티 동적 생성
let newPlayer = {
  level: 50,
};
newPlayer.job = "healer";
console.log(newPlayer); // {level: 50, job: 'healer'}

//프로퍼티 삭제
delete newPlayer.job;
console.log(newPlayer); // {level: 50}
```

---

### 책속 한구절 보관함 📖

> p. 124
> 프로퍼티 값이 함수일 경우, 일반 함수와 구분하기 위해 메서드라고 부른다.

> p. 124
> 자바스크립트의 객체는 함수와 밀접한 관계를 가진다. 함수와 객체는 분리해서 생각할 수 없는 개념이다. 즉, 객체를 이해해야 함수를 제대로 이해할 수 있고 반대로 함수를 이해해야 객체를 정확히 이해할 수 있다.

<br>

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
인스턴스 :
클래스에 의해 생성되어 메모리에 저장된 실체. 객체지향 프로그램에서 객체는 클래스, 인스턴스를 포함하는 개념이다. 클래스는 인스턴스를 생성하기 위한 템플릿의 역할을 한다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
메서드가 상태 데이터의 행동 즉, 함수라는 건 알고 있었으나 프로퍼티 내의 함수를 일반 함수와 구분 짓기 위해 메서드라고 구분 지어 부른다는 건 오늘에야 처음 알았다. 그간 TIL을 정리하며 함수와 메서드를 왔다갔다 썼는데(...) 반성 중이다.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
-메서드 축약 표현으로 정의한 메서드는 프로퍼티에 할당한 함수와 다르게 동작한다. <- 이 의미가 궁금하다. 예시를 찾아봐야겠다.

-자바스크립트 프로퍼티 동적 생성을 하게 되면 코드가 좀 혼란스러워지지 않을까 생각이 드는데, 현업이나 프로젝트에서 쓰이는 경우가 있을까? 쓰인다면 어떤 식으로 쓰일까?
```
