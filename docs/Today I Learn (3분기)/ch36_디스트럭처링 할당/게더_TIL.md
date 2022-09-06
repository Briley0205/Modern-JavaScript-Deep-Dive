## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.06

**오늘 읽은 범위** : 36장 디스트럭처링 할당

### 구조 분해 할당 📑

- 구조화된 [이터러블 또는 객체]를 비구조화=구조파괴 하여 1개 이상의 변수에 개별적으로 할당하는 것. 필요한 값만 추출해서 사용할 때 좋다.

1. 배열 디스트럭처링

```js
const array = [1, 2, 3];
// 이건 배열 리터럴

const [one, two, three] = array;
// 이건 배열 디스트럭쳐링
// 할당 연산자 왼쪽엔 값을 할당받을 변수를 배열 리터럴 형태로 선언
// 할당 연산자 오른쪽엔 비구조화할 배열의 식별자. 이터러블이 아니면 에러가 난다.
```

- 배열 디스트럭처링의 기준은 인덱스다. 순서대로다.
- 변수의 개수와 이터러블의 요소개수가 반드시 일치할 필요는 없다. 많으면 그냥 undefined를 반환한다.
- 함수에 인수 넣을때처럼 기본값과 rest파라미터 이용이 가능하다. 이때 rest는 반드시 마지막에 위치할 것

2. 객체 디스트럭처링

```js
const user = { firstName: "Jay", lastName: "blue" };
const name = user.firstName;
const family = user.lastName;
// 이런식으로 프로퍼티 키를 기준으로 개별 할당 가능

const { lastName, firstName } = user;
// 한꺼번에 불러오고 싶다면 이렇게 프로퍼티 키를 입력해야 한다.
// 순서는 상관없고 프로퍼티 키를 기준으로 불러오기에 에러가 적다.

const { lastName: last, firstName: first } = user;
// 내가 원하는 이름으로 값을 할당받고 싶다면 다음과 같이 만들어주면 last, first로 불러올 수 있다.
```

- 배열 디스트럭처링과 달리 키를 기준으로 판단하기에 순서를 외울 필요가 없다.
- 역시 기본값과 rest파라미터 이용이 가능하다.
- 프로퍼티 키를 매개체로 값만 소환해서 변수에 담고 싶을때 유용하다.
- 객체를 인수로 전달받는 함수의 매개변수 부분에도 사용할 수 있다. 일일이 .을 안써도 되어서 가독성이 조금 올라간다.

3. 배열의 요소가 객체인 경우 디스트럭쳐링 예제

```js
const todos = [
  { id: 1, content: "html1" },
  { id: 2, content: "html2" },
  { id: 3, content: "html3" },
];
const [, { id }] = todos;
// todos 배열의 2번째 인덱스의 id값만 추출
```

4. 객체가 중첩객체일 경우 디스트럭쳐링 예제

```js
const user = {
  name: "user",
  address: { zipCode: "23423", city: "Seoul" },
};

const {
  address: { city },
} = user;
// user의 address값의 city만 추출
```
