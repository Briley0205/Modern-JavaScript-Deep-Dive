## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.14

**오늘 읽은 범위** : 21장 빌트인 객체


## 21.1 자바스크립트 객체의 분류
> 표준 빌트인 객체
- ECMAScript 사양에 정의된 객체
- 애플리케이션 전역의 공통의 기능
- 별도의 선언 없이 전역 변수처럼 언제나 참조 가능

> 호스트 객체
- ECMAScript 사양에 정의되어 있지 않지만 자바스크립트 실행 환경에서 추가로 제공하는 객체

> 사용자 정의 객체
- 사용자가 직접 정의한 객체

## 21.2 표준 빌트인 객체
- Math, Reflect, JSON을 제외한 표준 빌트인 객체는 모두 인스턴스를 생성할 수 있는 생성자 함수 객체
- 인스턴스의 프로토타입은 표준 빌트인 객체의 prototype 프로퍼티에 바인딩된 객체

## 21.3 원시값과 래퍼 객체
- 래퍼 객체: 문자열, 숫자, 불리언 값에 대해 객체처럼 접근하면 생성되는 임시 객체

## 21.4 전역 객체
- 어떤 객체에도 속하지 않은 최상위 객체
```
- 전역 객체는 개발자가 의도적으로 생성할 수 없다.
- 전역 객체의 프로퍼티를 참조할 때 window(또는 global)를 생략할 수 있다.
```

### 21.4.1 빌트인 전역 프로퍼티
- Infinity, NaN, undefined

### 21.4.2 빌트인 전역 함수
- eval: 자바스크립트 코들르 나타내는 문자열ㅇ르 인수로 전달 받아 런타임에 평가하여 값을 생성
- inFinite: 전달받은 함수가 정상적인 유한수인지 검사하여 유한수이면 true를 반환, 무한수이면 false를 반환
- isNaN: 전달받은 인수의 타입이 숫자가 아닌 경우 숫자로 타입을 변환한 후 검사 수행
- parseFloat: 전달받은 문자열 인수를 부동 소수점 숫자, 즉 실수로 해석하여 반환
- parseInt: 전달받은 무장려 인수를 정수로 해석하여 반환
