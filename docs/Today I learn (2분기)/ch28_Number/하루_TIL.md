## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.29

**오늘 읽은 범위** : 28장 Number

# Number

+ 메서드의 이름과 쓰임새가 같더라도 Number 메서드와 빌트인 전역함수엔 차이가 있다.
   + Number 메서드는 전역함수와 달리 전달받은 인수를 숫자로 암묵적 타입 변환하지 않는다. 숫자가 아닌 인수가 주어지면 언제나 false 다.
```javascript
// 인수가 정수이면 true를 반환한다.
Number.isInteger(0)     // -> true
Number.isInteger(123)   // -> true
Number.isInteger(-123)  // -> true

// 0.5는 정수가 아니다.
Number.isInteger(0.5)   // -> false
// '123'을 숫자로 암묵적 타입 변환하지 않는다.
Number.isInteger('123') // -> false
// false를 숫자로 암묵적 타입 변환하지 않는다.
Number.isInteger(false) // -> false
// Infinity/-Infinity는 정수가 아니다.
Number.isInteger(Infinity)  // -> false
Number.isInteger(-Infinity) // -> false
```

</br>

