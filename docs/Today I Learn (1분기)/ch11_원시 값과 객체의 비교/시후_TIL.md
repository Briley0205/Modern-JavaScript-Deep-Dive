## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.21

**오늘 읽은 범위** : 11장 원시 값과 객체 비교

### 값의 보호와 복사의 종류 📑

- 한 번 생성된 원시 값은 읽기 전용값으로서 변경할 수 없다.
- 복사 시, 변수에는 값이 저장되는 것이 아니라 메모리 주소가 전달된다.
- 전달 유형에 따라 값에 의한 전달(공유에 의한 전달)과 참조에 의한 전달(값에 의한 전달)로 나뉜다.

---

|  | 원시 타입 (premitive type) | 객체 타입 (object / refrence type)  |
| ---- | ------ |----|
| 값의 종류 | 변경 불가능한 값 (immutable value) | 변경 가능한 값 (mutable value) |
| 저장 내용 | 실제 값 저장 | 참조 값(메모리 주소) 저장 |
| 전달 방식 | 값에 의한 전달 | 참조에 의한 전달 |


### 새로운 단어 정리 🔖
```js
유사 배열 객체(array-like object)
 : 배열과 같이 인덱스([])로 프로퍼티 값에 접근할 수 있고,
 length 프로퍼티를 갖는 객체를 말한다.

 + 문자열이 이에 해당한다.
 단, 이미 생성된 문자열의 일부 문자를 변경해도 반영되지 않는다.

얕은 복사와 깊은 복사(shallow copy and deep copy)
 : 원본과는 참조 값이 다른 별개의 객체이다.

 얕은 복사 = 객체 안에 중첩되어 있는 객체는 참조 값을 복사
 깊은 복사 = 객체 안에 중첩되어 있는 객체까지 모두 복사 
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭
```
요즘 들어 api를 통해 다른 서버에서 데이터 오브젝트를 받아오는
경우가 늘었다. (axios, graphQL 만세!)

때문에 가져온 데이터(객체)를 다루는 레시피에 관심이 간다.
요청한 데이터를 가지고 이런저런 형태(데이터 타입 변경 등)로 
요리해 써먹은 적은 있어도, 내용을 바꿔서 써본 적은 없는 듯 하다.

...

```

---

### 다른 분이 작성하신 TIL에 대한 소감