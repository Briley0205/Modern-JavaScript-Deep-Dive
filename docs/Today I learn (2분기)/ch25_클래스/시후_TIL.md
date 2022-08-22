## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.15 - 17

**오늘 읽은 범위** : 25장 클래스

### 객체 설계도 클래스 📑

- JS를 통한 객체지향 프로그래밍에 깊이 빠지고 싶은 때 사용한다.
- 클래스 또한 값처럼 사용할 수 있는 일급 객체다.
- 클래스 상속은 기존 클래스를 상속바다아 사로운 클래스를 확장하는 것이다.

---

### 클래스 vs 생성자 함수

> 클래스와 생성자 함수 모두 프로토타입 기반의 인스턴스를 생성한다.

|  | 클래스 | 생성자 함수 |
|----|----|----|
| new 없이 호출 | 에러 발생 | 일반 함수로 호출 |
| extends / super | O | X |
| 호이스팅 | 발생하지 않는 것처럼 동작 | 발생한다 |
| strict mode | 클래스 내 전역에서 '무조건' 적용 | 선택적 적용 |
| [[ Enumerable ]] | false | true (선택적) |

++ 이처럼 클래스는 다른 함수보다 견고하고 명료하여 typescript랑 같이 쓰면</br>
훨씬 엄격한 문법적 시너지를 맛볼 수 있다.

```js
class DrawAnimal {
    animal: string;
    color: string;
    constructor(options: {animal: string, color: string}) {
        this.animal = options.animal;
        this.color = options.color;
    }
    // 프로토타입 메서드
    printAnimal() {
        console.log(`I drew a ${this.color} ${this.animal}`);
    }
    // 정적 메서드
    static printAnimal() {
        console.log(`I drew a ${this.color} ${this.animal}`);
    }
    get printAnimal() {
        return `${this.color} ${this.animal}`;
    }
}
const animalPrinting = new DrawAnimal("rabbit", "white");
animalPrinting.printAnimal();
```

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```js
클래스 필드(class field) {
    클래스 기반 객체지향 언어에서 클래스가 생성할
    인스턴스의 프로퍼티를 가리키는 용어이다.
}
```
