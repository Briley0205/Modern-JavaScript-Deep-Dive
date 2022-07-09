## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.05.

**오늘 읽은 범위** : 2장 2.1 ~ 2.5

### 자바스크립트의 역사

- JS는 객첵반의 스크립트 프로그래밍 언어
- 웹브라우저 내에서 주로 사용되며 Node.js와 같은 런타임 환경과 같이 서버 프로그래밍에도 사용
- 자바스크립트는 ECMA 스크립트의 표준 사양을 가장 잘 구현한 언어로 인정받고 있다.

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
프로토타입 : JS는 객체를 상속하기 위하여 프로토타입이라는 방식을 사용한다. 모든 객체들이 메소드와 속성들을 상속받기 위한 템플릿으로써 프로토타입 객체를 가진다는 의미이고, 프로토타입 객체도 또 다시 상위 프로토타입 객체로부터 메소드와 속성을 상속 받을 수 도있고, 그 상위 프로타타입까지 마찬가지이다.
```

```js
// 생성자 함수 정의
function Person(first, last, age, gender, interests) {
  this.first = first;
  this.last = last;
  this.age = age;
  this.gender = gender;
  this.interests = interests;
}

// 인스턴스 생성
const BBAKJUN = new Person("JunHyeong", "Park", 27, "male", [
  "websocket",
  "Nest.Js",
  "React.js",
  "OOP",
  "FP",
]);
```

![](https://velog.velcdn.com/images/wnsguddl789/post/106425ca-b2d7-40bf-9f00-d2674885631c/image.png)

```
위에서 BBAKJUN의 프로토타입 객체인 Person() 에 정의된 멤버들들이 보인다
- first, last, age, gender, interests
```

![](https://velog.velcdn.com/images/wnsguddl789/post/2558e80a-37d6-4fee-bdd3-de5ed089dad0/image.png)

```
또한 watch, valueOf 처럼 Person()의 프로토타입 객체인 Object에 정의된 다른 멤버들도 확인이 가능하다

```

[MDN Object](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object) 에서 확인가능

![](https://velog.velcdn.com/images/wnsguddl789/post/512ff2a5-3eda-4aa2-bab6-248e0e91eec5/image.png)

```
실제로 Object에 정의되어있는 메서드를 BBAKJUN에서 호출하게 되면 호출된 객체의 값을 단순 반환하게된다.
이때 일어나는 일의 순서는 아래와 같다.

> 브라우저는 우선 BBAKJUN 객체가 valueOf() 메소드를 가지고 있는지 체크합니다.

> 없으므로 BBAKJUN의 프로토타입 객체(Person() 생성자의 프로토타입)에 valueOf() 메소드가 있는지 체크합니다.

> 여전히 없으므로 Person() 생성자의 프로토타입 객체의 프로토타입 객체(Object() 생성자의 프로토타입)가 valueOf() 메소드를 가지고 있는지 체크합니다. 여기에 있으니 호출하며 끝납니다!
```

![](https://velog.velcdn.com/images/wnsguddl789/post/60176c95-cbb8-4496-9214-9c16658589b5/image.png)

```
Person 객체와 Object 객체의 Prototype을 확인해보았다.

커스텀 생성자 프로타티입 Person에는 출력되는것이 많지않을것인데, 아무것도 정의하지 않았기때문이다.

그에 비해 Object에서는 사용 가능한 수 많은 메서드들이 이미 정의되어있다.

JS 전반에 걸쳐 프로토타입 체인 상속이 어떻게 구성되어있는지 확인이 가능했고,
비슷한 예로 전역 객체인 String, Number, Date, Array의 프로토타입에 정의된 메서드들도 많은것을 예상해볼수 있었다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
웹개발에 처음 입문했던 2016년 멋쟁이사자처럼때 부터 JS를 더욱 열심히 공부했었다면,,? 더 나은 개발자가 되었을수도 있겠다는 생각이 듭니다.

최근 JS에서 TS로 넘어가며 공부중인데, TS 요놈 정말 물건이거같습니다.
특히나 null / undefined에게 엄격한걸 보고 사내프로젝트에도 얼른 적용시키고 싶은 마음이 들어요.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
JavaScript 에서 객체지향을 하느냐? 함수지향을 하느냐? 그것이 궁금합니다.
함수형이 최근 새로운 패러다임으로 등장했으나, 단단하였던 객체지향을 이길만큼의 메리트가 있는지? 그것이 궁금함
```

---

### 다른 분이 작성하신 TIL에 대한 소감
