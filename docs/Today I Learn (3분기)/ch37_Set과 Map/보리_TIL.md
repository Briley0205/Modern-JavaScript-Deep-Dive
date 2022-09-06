　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.06

**오늘 읽은 범위** : 37장 set , map

### Set ? 
+ 중복되지 않는 유일한 값들의 집함을 Set이라 함! 배열과 유사하지만 차이가 있음.
+ Set을 통해 교집합, 합집합, 차집합, 여집합 등을 구현할 수 있음.
```js
//set생성
const set = new Set();
console.log(set); //set(0)
```
+ 이터러블을 인수로 전달받아 set객체를 생성. 중복된 값은 요소로 저장되지 않음.

#### 요소 개수 확인
+ Set.prototype.size로 확인가능

#### 요소 추가
+ Set.prototype.add 로 추가가능

#### 요소 존재 여부 확인
+ Set.prototype.has를 사용 : boolean값을 반환함

#### 요소 삭제
+ Set.prototype.delete : boolean값을 반환, 인덱스가 아니라 삭제하려는 요소 값을 인수로 전달 해야함.

#### 요소 일괄 삭제
+ Set.prototype.clear 사용

#### 요소 순회
+ Set.prototype.forEach를 사용
+ Array의 forEach와 유사하게 콜백함수와 forEach메서드의 콜백 함수 내부에서 this로 사용될 객체를 인수로 전달함. 인수는 3개 받음
+ 첫번째 인수 : 현재 순회 중인 요소값
+ 두번째 인수 : 현재 순회 중인 요소값
+ 세번째 인수 : 현재 순회 중인 Set객체 자체

### 집합 연산
+ 수학적 집합을 구현하기 위한 자료구조.
+ 따라서 Set객체를 통해 교집합, 합집합, 차집합 등을 구현할 수 있음. p.649확인

### Map ?
+ 키와 값의 쌍으로 이루어진 컬렉션

#### map객체 생성
```js
const map = new Map();
```
+ 이터러블을 인수로 전달 받아 Map객체를 생성함. 이때 인수로 전달되는 이터러블은 키와 값의 쌍으로 이루어진 요소로 구성되어야 함

#### 요소 개수 확인
+ Map.prototype.size 를 사용

#### 요소 추가
+ Map.prototype.set 을 사용

#### 요소 취득
+ Map.prototype.get을 사용. 

#### 존재 여부 확인
+ Map.prototype.has : boolean값으로 반환

#### 요소 삭제
+ Map.prototype.delete : boolean값으로 반환

#### 요소 순회
+ set과 별다를건 없지만 두번째 인수는 요소키를 전달받음.

---

### 책속 한구절 보관함 📖

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 659  | Map객체는 이터러블이면서 동시에 이터레이터인 객체를 반환하는 메서드를 제공한다. |

