## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.19

**오늘 읽은 범위** : 10장 객체 리터럴

### JS의 핵심 구성요소, 객체 📑

- JS엔진의 객체 생성 방식은 크게 (객체 리터럴 / 함수) 두 가지로 나뉜다.
- 객체는 프로퍼티의 집합으로, 프로퍼티 키 / 값으로 구성된다.
- 객체 생성과 동시에 프로퍼티를 만들 수 있고, 자유롭게 가감(加減)할 수 있다.

---
### 객체 생성 방식

> 객체 리터럴 && 함수로 생성

중괄호를 통해 0개 이상의 프로퍼티를 정의</br>
+이 때 중괄호는 코드블럭을 의미하지 않는다 🔄 값으로 평가되는 표현식이다.

---
### 프로퍼티 🎨

- 프로퍼티 키 : 프로퍼티 값에 접근할 수 있는 식별자
- 프로퍼티 값 : JS에서 사용할 수 있는 값

** 프로퍼티 키를 중복 선언하면, <strong>무조건 나중에 선언된 것이 덮어쓴다.</strong>

> ES6 확장 기능
```js
 변수 이름 = 프로퍼티 키 ---> 생략 가능
 const username = Shihu
 let age = 21
 const user = {username, age};
 console.log(user); // {username: Shihu, age: 21}

 계산된 프로퍼티 이름(computed property name)

 const Writer = "Shihu";
 let TILname = 0;
 const TIL = {
    [`${Whiter}_제${++TILname}장_TIL`]: TILname,
    [`${Whiter}_제${++TILname}장_TIL`]: TILname,
    [`${Whiter}_제${++TILname}장_TIL`]: TILname
 }

 메서드 정의 시 function 키워드 축약 가능
```

### 새로운 용어 정리 🔖
```js
클래스 : 다른 객체를 만드는 틀 (템플릿)
인스턴스 : 클래스에 의해 생성되어 메모리에 저장된 실체

인형을 만들어내는 생성자 함수(constructor)가 있다.
이 함수로 만들어낸 인형을 인스턴스라 한다.

ex) function Doll(color, animal) {
    this.color = color;
    this.animal = animal;
    this.is = function() {
        console.log(`This is ${this.color} ${this.animal} doll!`)
    }
    // 내부에서 사용한 this 키워드는 객체 자신을 가리키는 참조변수다.
}
const blueDoll = new Doll('blue', 'whale');
blueDoll.is(); // This is blue whale doll!
```

### 책속 한구절 보관함 📖

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 124 | 원시 타입은 단 하나의 값만 나타내지만 객체 타입은 다양한 타입의 </br>값을 하나의 단위로 구성한 복합적인 자료구조다.</br> 또한 객체 타입의 값은 변경 가능한 값이다. |
| 127 | 객체 리터럴에 프로퍼티를 포함시켜 객체를 생성함과 동시에 프로퍼티를 만들 수도 있고,</br> 객체를 생성한 이후에 프로퍼티를 동적으로 추가할 수도 있다. |

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭
```
다른 언어에서 클래스를 사용해본 경험이 적어서인지,
클래스로 생성할 수 있는 인스턴스에 대해 이해하기 힘들었다.
객체는 클래스와 인스턴스를 아우르는 개념이니,
객체를 이해하기 위해서 제대로 짚고 넘어가야겠다.
```

---

### 다른 분이 작성하신 TIL에 대한 소감