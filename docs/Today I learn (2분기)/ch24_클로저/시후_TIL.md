## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.11

**오늘 읽은 범위** : 24장 클로저

### 함수가 기억하는 상위 스코프 📑

- 자신이 선언된 환경을 기억하고 참조하는 모든 함수는 클로저다.
- 하지만, 생명 주기가 종료된 상위 스코프의 식별자를 참조하지</br> 않는 함수는 클로저가 아니다.
- 클로저는 특정 함수에만 상태 변경을 허용하여 상태를 안전하게</br> 변경 / 유지하기 위해 사용한다.
---

### [[ Environment ]] 내부슬롯 🎞

```
함수가 평가되는 시점, 맨 처음 함수 객체가 생성될 때
[[ Environment ]] 내부슬롯에 상위 스코프(렉시컬 환경)을 기록한다.
이를 통해 외부 함수의 생존 여부와 상관 없이 자신이 정의된 위치에 
의해 결정된 상위 스코프를 기억한다.
```

### 클로저의 속성 🎁

> 클로저란, 중첩 함수가
1. 상위 스코프의 식별자를 참조하며
2. 외부 함수(상위 스코프) 보다 더 오래 생존하는것

을 의미한다.

---

### 다른 분이 작성하신 TIL에 대한 소감