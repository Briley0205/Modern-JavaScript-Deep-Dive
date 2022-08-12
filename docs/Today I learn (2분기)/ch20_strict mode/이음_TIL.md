## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.12

**오늘 읽은 범위** : 20장 strict mode

### 20.1 strict mode란?

- 암묵적 전역
- stict mode는 자바스크립트 언어의 문법을 엄격히 적용, 잠재적 오류 원인 리포팅
- ESLint 린트 도구는 더욱 강력한 효과

### 20.2 stict mode의 적용
- 함수 몸체의 선두에 'use strict' 추가

### 20.3 전역에 stict mode 를 적용하는 것은 피하자
- 외부 서드파티 라이브러리가 non-strict mode인 경우도 있기 때문에 전역에 stict mode를 적용하는 것은 바람직하지 않음

### 20.4 함수 단위로 stict mode를 적용하는 것도 피하자
- 즉시 실행 함수로 감싼 스크립트 단위로 적용하는 것이 바람직

### 20.5 stict mode가 발생시키는 에러
- 암묵적 전역
- 변수, 함수, 매개변수의 삭제
    - delete 연ㅅ나자로 변수, 함수, 매개변수를 삭제하면 SyntaxError 발생
- 매개변수 이름의 중복
- with 문의 사용

### 20.6 stict mode 적용에 의한 변화
> 일반 함수의 this
- 함수를 일반 함수로서 호출하면 undefined가 바인딩
> arguments 객체
- 매개변수에 전달된 인수 재할당해도 arguments 객체에 반영 x

