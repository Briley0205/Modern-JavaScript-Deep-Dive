## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.09.21

### 47장 에러 처리 📑

---
### 에러 처리의 필요성
에러를 방치하거나 예외적 상황에 대응하지 않으면 프로그램은 강제 종료된다. 따라서 작성한 코드에는 언제나 에러나 예외적 상황이 발생할 수 있다는 것을 전제하고 이에 대응하는 코드를 작성하는 것이 중요하다.

---
### try...catch...finally
에러 처리 코드를 미리 등록해두고 에러가 발생하면 그 코드로 점프하는 방법. 이를 `에러 처리` 라고 하는데 try...catch...finally문은 3개의 블록으로 구성된다.
```Js
try{
    //실핼할 코드
} catch(err){
    //try에서 에러 발생 시 실행될 코드
} finally{
    //에러 발생 상관없이 반드시 한 번 실행
}
```
이는 프로그램의 강제 종료를 막을 수 있다.

---
### Error 객체
```js
const error = new Error('invalid');
// 에러를 상세히 설명하는 에러 메세지를 인수로 전달할 수 있다.
```
- message 프로퍼티<br>
Error 생성자 함수에 인수로 전달한 에러 메세지
- stack 프로퍼티<br>
에러를 발생시킨 콜스텍의 호출 정보를 나타내는 문자열 - 디버깅으로 사용

| 생성자 함수 | 인스턴스 |
|----------|---------|
|Error|일반적인 에러 객체|
|SyntaxError|자바스크립트 문법에 맞지 않는 문을 해석 시 발생|
|ReferenceError|참조할 수 없는 식별자를 참조했을 때 발생|
|TypeError|피연산자 또는 인수 데이터 타입이 유효하지 않을 때|
|RangeError|숫자값의 허용 범위를 벗어났을 때|
|URIError|encodeURI 또는 decodeURI 함수에 인수가 부적절하게 전달되었을 때|
|EvalError|eval 함수에서 발생하는 에러|

---
### throw 문
에러 객체를 생성하는 것과 에러를 발생시키는 것은 의미가 다르다. 에러를 발생시키려면 try 코드 블록에서 throw문으로 에러 객체를 던져야한다.

throw문의 표현식은 어떤 값이라도 상관없지만 일반적으로 에러 객체를 지정한다. 에러를 던지면 catch문의 에러 변수가 생성되고 던져진 에러 객체가 할당된다. 그 후 catch 코드 블록이 실행된다.
```Js
try{
    //실핼할 코드
    throw new Error('some Error");
} catch(err){
} 
```

---
### 에러의 전파
에러는 호출자 방향으로 전파된다. 즉, 콜 스택의 아래 방향으로 전파된다.

---