## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.11

**오늘 읽은 범위** : 20장 strict mode

## strict mode 란

- 자바스크립트 언어의 문법을 좀 더 엄격히 적용하여 오류를 발생시킬 가능성이 높거나 자바스크립트 엔진의 최적화 작업에 문제를 일으킬 수 있는 코드에 대해 명시적인 에러를 발생시킨다.
- ESLint와 같은 린트 도구를 사용해도 strict모드와 유사한 효과를 얻을 수 있다.
- strict모드 보다는 린트 도구를 사용하는 것을 추천
- strict모드를 전역에 적용하는 것은 피할 것
  - 외부 서드파티 라이브러리를 사용하는 경우가 non-strict mode인 경우도 있기 때문
- 함수 단위로 strict mode를 적용하는 것도 피하자
  - 함수 단위로 일일이 적용해야함(귀찮음)
  - 함수 외부 컨텍스트에 strict mode를 적용하지 않는다면 이 또한 문제가 발생할 수 있음

## strict mode가 발생시키는 에러

- 암묵적 전역
- 변수, 함수, 매개변수의 삭제
- 매개변수 이름의 중복
- with 문의 사용

## strict mode 적용에 의한 변화

- 일반 함수의 this
  - 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩된다. 생성자 함수가 아닌 일반 함수 내부에서는 this를 사용할 필요가 없기 때문. 이 때 에러는 발생하지 않음

## arguments 객체

- strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않는다.

## 결론

- 린트 짱 린트 최고
