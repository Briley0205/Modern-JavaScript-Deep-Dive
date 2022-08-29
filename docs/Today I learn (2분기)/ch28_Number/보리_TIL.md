## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.29

**오늘 읽은 범위** : 28장 Number

### Number 생성자 함수
+ Number는 원시 타입인 숫자를 다룰때 유용한 프로퍼티와 메서드를 제공!
+ new 연산자와 함께 호출하면[[NumberData]]내부 슬롯에 0을 할당한 Number래퍼 객체를 생성함.

### Number 프로퍼티
1. Number.EPSILON : ES6도입, 1과 1보다 큰 숫자 중에서 가장 작은 숫자와의 차이와 같음. 2진법으로 변환 시 무한 소수가 됨(오차발생)
2. Number.MAX_VALUE : JS에서 표현할 수 있는 가장 큰 양수 값 < Infinity
3. Number.MIN_VALUE : JS에서 표현할 수 있는 가장 작은 양수 값 > 0
4. Number.MAX_SAFE_INTEGER : JS에서 안전하게 표현할 수 있는 가장 큰 정수 값
5. Number.MIN_SAFE_INTEGER : 안전하게 표현할 수 있는 가장 작은 정수 값
6. Number.POSITIVE_INFINITY : 양의 무한대를 나타내는 숫자 값
7. Number.NEGATIVE_INFINITY : 음의 무한대를 나타내는 숫자 값
8. Number.NaN : Not a number

### Number 메서드
1. Number.usFinite : 인수로 전달된 숫자값이 정상적인 유한수인지 아닌지 검사하여 그 결과값을 불리언 값으로 반환
2. Number.inInteger : 인수로 전달된 숫자값이 정수인지 검사하여 불리언 값으로 반환
3. Number.isNaN : 인수로 전달된 숫자값이 NaN인지 검사하여 불리언 값으로 반환
4. Number.isSafeInteger : 인수로 전달된 숫자값이 안전한 정수인지 검사하여 결과를 불리언 값으로 반환, 안전한 정수값은 -(2의53 - 1) 과 2의53 - 1 사이의 정수값
5. Number.prototype.toExponential : 숫자를 지수 표기법으로 변환하여 문자열로 반환
6. Number.prototype.toFixed : 숫자를 반올림하여 문자열로 반환, 반올림하는 소수점 이하 자릿수를 나타내는 0~20사이의 정수값을 인수로 전갈 가능
7. Number.prototype.toString : 숫자를 문자열로 반환하여 반환함. 인수를 생략하면 10진법이 지정됨.

---
