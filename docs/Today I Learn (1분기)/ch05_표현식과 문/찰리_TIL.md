## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.11

**오늘 읽은 범위** : 5장 표현식과 문

### 컴퓨터 공학 용어 📑

---

### 책속 한구절 보관함 📖

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 53 | 값으로 평가될 수 있는 문은 모두 표현식이다       |



### 용어 대정리 (세 줄 요약 불가..!) 🔖
- `값value` : 표현식이 평가되어 생성된 결과
```javascript
var value = 10;
// value 는 변수, 10이 값
```

- `리터럴literal` : 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법
- `표현식expression` : 값으로 평가될 수 있는 문 
```javascript
var score = 100;
// 100은 정수 리터럴, 값으로 활용할 수 있기 때문에 표현식이다.
```

- `문statement` : 프로그램을 구성하는 기본 단위이자 최소 실행 단위 즉 컴퓨터에 내리는 명령
  - 표현식인 문과 아닌 문의 구분 : 할당이 가능한지의 여부에 따라 가능하면 표현식, 아니면 표현식이 아니다.
- `토큰token` : 문법적인 의미를 가지며, 문법적으로 더이상 나눌 수 없는 코드의 기본 요소
```javascript
var x; // 변수 선언문
x = 5; // 할당문
function foo () {} // 함수 선언문
if (x > 1) { console.log(x); } // 조건문
for (var i = 0; i < 2; i++) { console.log(i); } // 반복문
```

- `세미콜론` : 문의 종료
  - 세미콜론 자동 삽입 기능(ASI) : 자바스크립트 엔진이 소스코드를 해석할 때 문의 끝이라고 예측되는 지점에 세미콜론을 자동으로 붙여주는 기능


---

### 다른 분이 작성하신 TIL에 대한 소감

