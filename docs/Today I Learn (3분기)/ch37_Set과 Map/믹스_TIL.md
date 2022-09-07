## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.09.06

### 37장 Set과 Map 📑

---
### Set
> 중복되지 않는 유일한 값들의 집합으로 배열과 유사하지만 동일한 값을 중복 포함할 수 없고-이를 이용해 배열에서 중복된 요소를 제거할 수 있다.-
요소 순서에 의미가 없으며 즉 인덱스로 접근이 불가능하다.

---
### Set 객체의 생성
Set객체는 Set 생성자 함수로 생성한다. 인수를 전달하지 않으면 빈 객체가 생성된다.
Set 생성자 함수는 이터러블을 인수로 전달받아 Set 객체를 생성한다.
```js
const set = new Set();
console.log(set); // Set(0)[]
```

- Set.prototype.size -
Set 객체의 요수 개수
- Set.prototype.add - 
Set 객체의 요수 추가
- Set.prototype.has - 
Set 객체의 요수 존재 여부 확인
- Set.prototype.delete - 
Set 객체의 요수 삭제
- Set.prototype.clear - 
Set 객체의 요수 일괄 삭제
- Set.prototype.forEach - 
Set 객체의 요수 순회

#### 집합 연산
Set 객체는 수학적 집합을 구현하기 위한 자료구조다. 따라서 Set 객체를 통해 교집합, 합집합, 차집합 등을 구현할 수 있다.

---
### Map
> 키와 값의 쌍으로 이루어진 컬렉션으로 객체와 유사하지만 객체를 포함한 모든 값을 키로 사용할 수 있고, 이터러블이며 요소 개수 확인 시 map.size를 사용한다.

### Map 객체의 생성
Map객체는 Map 생성자 함수로 생성한다. 인수를 전달하지 않으면 빈 객체가 생성된다.
Map 생성자 함수는 역시 이터러블을 인수로 전달받아 Map 객체를 생성한다. 이때 __인수로 전달되는 이터러블은 키와 값의 쌍으로 이루어진 요소로 구성되어야 한다.__
```js
const map = new Map();
console.log(set); // Map(0){}
```

- Map.prototype.size - 
Map 객체의 요수 개수
- Map.prototype.set -
Map 객체의 요수 추가
- Map.prototype.get - 
Map 객체의 요수 취득
- Map.prototype.has - 
Map 객체의 요수 존재 여부 확인
- Map.prototype.delete - 
Map 객체의 요수 삭제
- Map.prototype.clear -
Map 객체의 요수 일괄 삭제
-  Map.prototype.forEach -
Map 객체의 요수 순회