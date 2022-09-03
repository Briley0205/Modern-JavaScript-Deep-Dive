## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.04

**오늘 읽은 범위** : 33장 Symbol

## Symbol
- 다른 값과 중복되지 않는 유일무이한 값
- 이름의 충돌 위험이 없는 유일한 프로퍼티 키를 만들기 위해 사용한다.
- new 연산자와 함께 호출하지 않는다. 인스턴스를 생성하지 않기 때문이다.
- Symbol.for 메서드를 사용하면 전역에서 중복되지 않는 유일무이한 상수 심벌 값을 단 하나만 생성하여 전역 심벌 레지스트리를 통해 공유할 수 있다.\


### 사용 예시
```
// 위, 아래, 왼쪽, 오른쪽을 나타내는 상수를 정의한다.
// 이때 값 1, 2, 3, 4에는 특별한 의미가 없고 상수 이름에 의미가 있다.
const Direction = {
  UP: 1,
  DOWN: 2,
  LEFT: 3,
  RIGHT: 4
};

// 변수에 상수를 할당
const myDirection = Direction.UP;

if (myDirection === Direction.UP) {
  console.log('You are going UP.');
}
```

1,2,3,4 가 변경될 수 있고 다른 변수 값과 중복될 수 있기에, 변경/중복될 가능성이 없는 심벌 값으 사용할 수 있다.

```
// 위, 아래, 왼쪽, 오른쪽을 나타내는 상수를 정의한다.
// 중복될 가능성이 없는 심벌 값으로 상수 값을 생성한다.
const Direction = {
  UP: Symbol('up'),
  DOWN: Symbol('down'),
  LEFT: Symbol('left'),
  RIGHT: Symbol('right')
};

const myDirection = Direction.UP;

if (myDirection === Direction.UP) {
  console.log('You are going UP.');
}
```


