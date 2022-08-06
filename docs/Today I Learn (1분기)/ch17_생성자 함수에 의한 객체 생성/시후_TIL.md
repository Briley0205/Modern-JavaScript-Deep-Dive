## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.03

**오늘 읽은 범위** : 17장 생성자 함수에 의한 객체 생성

### 생성자 함수에 의한 객체 생성 📑

- 객체를 생성하는 방법 중에 Object 생성자 함수 / new 생성자 함수가 있다.
- new 생성자 함수로 프로퍼티 구조가 동일한 객체 여럿을 간편하게 찍어낼 수 있다.
- 함수 객체는 constructor / non-constructor 로 나뉘며, 그중 일부가 callable(호출할 수 있는) 함수이다.

---

### 생성자 함수(Constructor) 📫

> 객체를 생성하기 위한 일종의 틀이다.
```js
function BuildDoll(animal, color) {
    this.animal = animal;
    this.color = color;
    this.draw = function() {
        console.log(`I drew a ${this.color} ${this.animal}`);
    }
}
const blueDoll = new BuildDoll("dolphin", "blue");
const redDoll = new BuildDoll("dolphin", "red");
console.log(blueDoll.draw()); // I drew a blue dolphin
console.log(redDoll.draw()); // I drew a red dolphin
```
위 생성자 함수는 동물 그림 객체를 만든다.</br>
생성자 함수는 이처럼 프로퍼티 구조가 동일한</br>
객체 여러 개를 간편하게 생성한다.</br>
** + 생성자 함수 이름은 파스칼 노테이션을 따른다.</br>
ex) PascalNotation, Circle, OneTwoThree

> 인스턴스 생성 시 생성자 함수가 거치는 과정

1. 암묵적으로 빈 객체 생성 (미래에 반환할 인스턴스를 this에 바인딩)
2. 인스턴스에 프로퍼티 / 메서드 추가, 초기값 또는 고정값 할당
3. 생성자 함수 내부 준비 완료 시, 완성된 인스턴스를 암묵적으로 반환
4. 명시적으로 객체 반환시, 암묵적 this 반환 무시

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```
생성자 함수
 : new 연산자와 함께 호출하여 인스턴스(객체)를 생성하는 함수

this
 : 해당 객체 내부의 프로퍼티 / 메서드를 참조하기 위한 
 자기 참조 변수이다.

바인딩
 : 식별자와 값을 연결하는 과정
```

