## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.15

**오늘 읽은 범위** : 22장 this

### this 키워드

+ this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기참조 변수 입니다.
+ this를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있습니다.
+ JS엔진에 의해 암묵적으로 생성되며, 코드 어디서든 참고 가능!!
+ 함수내부에서 arguments객체를 지역변수처럼 사용할 수 있는 것처럼 this도 지역변수처럼 사용 가능!
+ 단 this가 가리키는 값, 즉 this바인딩은 함수 호출 방식에 의해 '동적'으로 결정됨
+ this 바인딩 : 식별자와 값을 연결하는 과정을 의미!


### 함수 호출 방식과 this 바인딩
1. 일반함수 호출 : 기본적으로 this에는 전역 객체가 바인딩 됩니다.
2. 메서드 호출 : 메서드를 호출할 때는 호출시점에 따라 결정됩니다. 주의사항: 메서드 내부의 this는 메서드를 소유한 객체가 아닌 메서드를 호출한 객체에 바인딩 된다는 것입니다.
3. 생성자 함수 호출 : 생성자 함수 내부의 this에는 생성자 함수가 생성할 인스턴스가 바인딩 됩니다.
4. Function.prototype.apply/call/bind메서드에 의한 간접 호출
+ apply, call, bind메서드는 Function.prototype의 메서드입니다.
+ 이 메서드는 모든 함수가 상속받아 사용 가능!
+ apply,call메서드의 본질적인 기능 ? '함수를 호출' 하는것
+ bind메서드는 메서드의 this와 메서드 내부의 중첩 함수 또는 콜백 함수의 this가 불일치하는 문제를 해결하기 위해 유용하게 사용!

---


### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
```js
//다른언어를 사용할때, 특히 JAVA를 하다가 JS를 하면 조금 혼란스러운게 사실입니다.. 너무 헷갈리는.. ㅎㅎ 명확히 공부를 해야겠습니다.
//1.우선 전역에서 this는 기본적으로 window객체
console.log(this); //window
//2.일반 함수에서 this도 window
function stdThis(){
  console.log(this);
}
stdThis();//window
//3.strict mode에서는 undefined
function stdThis(){
  'use strict'
  console.log(this);
}
stdThis(); //undefined
```
