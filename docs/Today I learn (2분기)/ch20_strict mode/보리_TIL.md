## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.14

**오늘 읽은 범위** : 20장 strict mode

### strict mode ?

+ ES5에 추가된 키워드. JS가 묵인했던 에러 메세지를 발생시키는 것. 
+ 즉 문법검사를 엄격하게 하는 것 입니다.

### strict mode의 적용
+ 전역의 선두 또는 함수 몸체에 선두에 'use strict';를 추가합니다.
+ 전역의 선두에 추가하면 스크립트 전체에 적용됩니다.
+ strict mode스크립트와 non-strict mode스크립트를 혼용하는 것은 오류를 발생 시킬수 있으니,
+ 전역에 strict mode를 적용하는 것은 피하는 것이 좋다 !
+ 함수 단위로 적용하는것도 피하는것이 좋다.
+ 함수 단위로 strict mode를 적용할 수 있지만, 어떤 함수는 strict mode를 적용하고, 어떤함수는 적용하지 않는것은 바람직 하지 않음!
+ 모든 함수에 strict mode를 사용하는것도 번거롭습니다.

### strict mode가 발생시키는 에러
1. 암묵적 전역 : 선언하지 않은 변수를 참조하면 ReferenceError가 발생
2. 변수,함수,매개변수 삭제 : delete 연산자로 삭제하면 Syntax Error가 발생
3. 매개변수 이름의 중복 : Syntax Error 발생
4. with문의 사용 : Syntax Error 발생
+ with문은 전달된 객체를 스코프 체인에 추가합니다. 동일한 객체의 프로퍼티를 반복해서 사용할 때 객체 이름을 생략할 수 있어,
+ 코드가 간단해 지지만, 성능과 가독성이 나빠지는 문제발생!

### strict mode 적용에 의한 변화
+ 일반 함수의 this
+ strict mode에서 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩 됨
+ 생성자 함수가 아닌 일반 함수 내부에서는 this가 필요 없기때문 ! 에러X

+ arguments 객체
+ strict mode에서는 매개변수에 전달된 인수를 재할당해 변경해도 arguments객체에 반영X


---

### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
```
ESLint사용 하는 것이...ㅎㅎ

```
