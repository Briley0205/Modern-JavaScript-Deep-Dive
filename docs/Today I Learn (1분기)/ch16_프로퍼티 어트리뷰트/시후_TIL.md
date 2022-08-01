## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.01

**오늘 읽은 범위** : 16장 프로퍼티 어트리뷰트

### 필요 없을 것 같았던 객체 상태 정리 📑

- 프로퍼티 어트리뷰트는 JS엔진 내부에서 사용하는, Read Only 값이다.
- 때에 따라서는, 프로퍼티 정의를 통해 재정의 가능 여부를 결정할 수 있다.
- 객체 변경을 방지하는 방안도 있다.

---

### 프로퍼티 어트리뷰트란 ? 📖

> 프로퍼티 생성 시 프로퍼티의 상태를 나타내기 위해 엔진에서 자동 정의 하는 것.
```js
const Shihu = {
    name: 'Shihu',
    age: 21
}
console.log(Object.getOwnPropertyDescriptor(Shihu, 'name'));
```
이 소스코드를 실행하면 콘손에 다음과 같은 프로퍼티 디스크립터 객체가 출력된다.
```js
{value: 'Shihu', writable: true, enumerable: true, configurable: true}
// {프로퍼티 값: 'Shihu', 갱신 가능 여부: boolean, 열거 가능여부: boolean, 재정의 가능 여부: boolean}
```
이것으로 프로퍼티의 상태에 관하여 간접적으로 '확인'할 수는 있지만,</br> 개발자가 이 값에 직접 손댈 수는 없다.</br>
이는 '데이터 프로퍼티'라고 할 수 있다.

### 접근자 프로퍼티 🔍

> 자체적인 값을 가지지 않고, 데이터 프로퍼티의 값을 </br>get / set 할 때 쓰는 접근자 함수 프로퍼티

```js
const me = {
    name: 'Shihu',
    age: 21,
    get introduce() {
        return `My name is ${this.name} and I'm ${this.age} years old.`
    },
    set introduce(name) {
        [this.name, this.age] = name.split(' ')
    }
}
console.log(me.introduce);
let descriptor = Object.getOwnPropertyDescriptor(me, 'introduce');
console.log(descriptor);
// {enumerable: true, configurable: true, get: ƒ, set: ƒ}
```

### 객체 변경 금지법 📜

`> 객체 확장 금지` : 동적 추가 금지

`> 객체 밀봉` : 읽기 / 쓰기 전용

`> 객체 동결` : 읽기 전용

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```js
프로퍼티 어트리뷰트
 : 프로퍼티 생성 시 프로퍼티의 상태를 나타내기 위해 자동으로 정의 하는 것.

데이터 프로퍼티
 : (키 / 값)으로 이루어진 일반적인 프로퍼티

접근자 프로퍼티
 : 자체적인 값을 가지지 않고 다른 데이터 프로퍼티의 값을 읽거나
 저장할 때 호출되는 접근자 함수로 구성된 프로퍼티

프로퍼티 정의
 : 프로퍼티 재정의 가능 여부 등을 결정할 수 있는 메서드
 Object.defineProperty(Array, 'PropertyKey', {
    key: 'value'
 })
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭
```js
사실 북클럽을 진행하기 앞서, 먼저 읽었을 땐, 
JS 라이브러리를 직접 만들 것이 아니라면, 
이 부분은 쓸모없기 짝이 없다고 생각했다.
하지만, 뒤에 나오는 챕터에서 빈번히 나오는 개념이므로,
한 번 확실히 짚고 넘어갈 필요가 있다고 생각했다.

스킵하고 싶어도 참고 정독하는 상황에서 다행히도(?)
다음 날, 프로퍼티 어트리뷰트를 스스로 확인하고,
내용 변경 불가 사유를 알아내야할 상황이 왔다.
(객체를 가져와서 프로퍼티를 구워삶으려(?) 했지만, 갱신할 수 
없었다. => 읽기 전용(동결된 객체) 이었다)

<>
생각해 보면 이 객체가 변경 가능한 객체인지, 확인하고 
넘어가야 할 때가 아주 많이 있었다. 두 달 전까지만 해도
객체 확장 제한 여부를 쭉 살피고 있었다.
그 때도 이걸 알고 있었더라면 더 좋았을텐데...
</>
```