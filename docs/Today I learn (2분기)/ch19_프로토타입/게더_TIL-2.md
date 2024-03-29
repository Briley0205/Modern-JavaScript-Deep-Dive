## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.11

**오늘 읽은 범위** : 19장 프로토타입 - 2!!

### 프로토타입 체인

- 자바스크립트는 객체의 프로퍼티에 접근하려고 할 때 해당 객체에 접근하려는 프로퍼티가 없으면 프로토타입 내부슬롯의 참조를 따라 자신의 부모 역할을 하는 프로토타입의 프로퍼티를 순차적으로 검색한다. 이를 프로토타입 체인이라고 한다.

- 프로토타입체인은 자바스크립트가 객체지향프로그래밍의 상속을 구현하는 메커니즘이다.

- 메서드를 호출하면 자바스크립트 엔진은 다음과 같은 과정을 거쳐 메서드를 검색한다.

1. 메서드를 호출하는 객체에서 해당 메서드를 검색한다.
2. 없으면 체인을 따라서 해당 프로토타입 내부 슬롯에 바인딩되어 있는 프로토타입으로 이동하여 해당 메서드를 검색한다.
3. 그 위에서도 없으면 가장상위의 Object.prototype으로 이동하여 검색한다.
4. 엔진이 메서드를 찾아내서 호출하며 이 때 Object.prototype.메서드의 this에는 제일 처음 탐색을 시작했던 그 객체가 바인딩된다.

- Object.prototype은 프로토타입 체인 최상단에 위치하는 객체로 오리지널 개념이고 따라서 모든 객체는 Object.prototype을 상속받는다. 뱀파이어 사회를 보는 것 같다.

- Object.prototype을 우리는 프로토타입 체인의 종점이라고 부르며 얘의 프로토타입 내부슬롯의 값은 null이다.

- 그치만 Object.prototype에서 체인을 타서 실패한 경우에도 undefined를 반환할 뿐 에러가 발생하지 않는 것에 주의하자.

### 스코프체인

- 지금까진 프로토타입 체인을 봤다.
- 프로퍼티가 아닌 식별자들은 스코프체인에서 검색된다.
- 자바스크립트 엔진은 함수의 중첩관계로 이루어진 스코프의 계층적 구조에서 식별자를 검색하며 스코프체인과 프로토타입 체인은 긴밀한 협력관계이다.

## 오버라이딩

- 프로토타입 프로퍼티와 같은 이름의 프로퍼티를 인스턴스에 추가하면 오버라이딩하면서 원래 있던게 가려진다. 이때 가려지는 현상을 프로퍼티 섀도잉이라 하고 덮어쓰는 것을 오버라이딩이라고 한다.
- 만약에 오버라이딩한걸 지우면 원래 있던게 다시 잘 보인다.

## 프로토타입의 교체

- 프로토타입은 객체이다.
- 모든 객체는 임의의 다른 객체로 변경될 수 있다.
- 이것은 객체간의 상속관계가 있더라도 이를 동적으로 변경가능하다는 의미이다.
- 프로토타입을 바꾸려면 생성자함수 또는 인스턴스를 이용하면 된다.

## 생성자함수로 프로토타입 바꾸기

- 생성자함수 + 객체리터럴로 재할당해줄 수 있다.
- 그러나 이걸 교체하면 constructor프로퍼티와 생성자함수간의 연결은 파괴된다.

## 인스턴스로 프로토타입 바꾸기

- ** proto** 를 사용해서 프로토타입을 바꿀 수 있다.
- 메서드 .setPrototypeOf(a, parent)를 이용할 수 있다.
- 마찬가지로 교체된 애는 constructor프로퍼티와의 연결을 잃는다.

## 결론

- 왠만하면 바꾸지 말기...
- 상속이 안전하다.

## instanceof

- 왼쪽에 객체, 옆에 생성자함수를 놔두면 true false값을 반환해준다.
- 생성자함수의 프로토타입에 바인딩된 객체가 왼쪽에 놔둔 객체의 프로토타입 체인상에 존재하면 true, 아니면 false를 반환한다.
- 함수 아닌걸 두면 에러가 난다.

## 직접 상속

- object.create를 쓰면 직접 상속이 가능하다.
- 원리는 새로운 객체를 만들며 만들때 지정된 프로토타입 및 프로퍼티를 갖게 하는 것이다.

- 하지만 이것도 남용하면 좋지 않다고 한다.
- create로 불러낼 수 있는 객체 중에는 최상위 객체도 있는데 얘는 체인의 종점이라 체인이 안먹으니까...

- 객체 리터럴 내부에서 ** proto**에 의한 직접 상속이 가능하다.
- 왠만하면 이걸 쓰자.

## 정적 프로퍼티/메서드

- 생성자함수로 인스턴스를 생성하지 않아도 참조/호출할 수 있는 프로퍼티/메서드를 말한다.
- 안에서 this를 안쓰면 정적 메서드로 사용해도 무방하다.

## 프로퍼티의 존재를 확인하고 싶을때

- "name" in person
- 이렇게 치면 불린값을 반환해준다.
- person.hasOwnProperty('name')
- 이렇게 해도 불린값을 반환해준다.

- for in 문은 프로퍼티 순회 열거에 아주 좋다.
- 배열에는 일반 for문이나 for of, forEach 문을 권장한다.

- Object.keys 메서드는 객체가 갖고 있는 프로퍼키 키를 배열로 반환해준다.
- Object.values 메서드는 객체가 갖고 있는 열거가능한 프로퍼티 값을 배열로 반환해준다.
- Object.entries 메서드는 키와 값의 쌍 배열을 배열에 담아서 반환해준다.

- 뒤에 2개는 es8에 생겼다 메모

## 후기

- 프로토타입은 참 길지만 객체를 다루는 메서드에 대해서 많이 알게되어 좋았습니다.
