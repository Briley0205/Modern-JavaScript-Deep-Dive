　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.19

**오늘 읽은 범위** : 46장 제너레이터와 async/await

### 제너레이터 ?

+ ES6에 도입. 코드블록의 실행을 일시 중지했다가 필요한 시점에 재개할 수 있는 특수 함수.
+ 일반함수와의 차이는 이렇게 있다.
1. 제너레이터 함수는 ㅎ마수 호출자에게 함수 실행의 제어권을 양도할 수 있다.
2. 제너레이터 함수는 함수 호출자와 함수의 상태를 주고받을 수 있다.
3. 제너레이터 함수를 호출하면 제너레이터 객체를 반환한다.

### 제너레이터 함수의 정의
+ function* 키워드로 선언한다. 
+ 하나 이상의 yield표현식을 포함한다. 이것을 제외하면 일반 함수를 정의 하는 방법과 같다.
```js
function* funcName(){
  yield 1;
}
```
+ 애스터리스크(*)의 위치는 function키워드와 함수 이름 사이라면 어디든지 상관 없음!
+ 하지만 function* 뒤에 바로 붙이는 것을 권장함.

### 제너레이터 객체
+ 제너레이터 함수를 호출하면 일반 함수처럼 함수 코드 블록을 실행하는 것이 아니라, 제너레이터 객체를 생성 해 반환한다.
+ 제너레이터 함수가 반환한 제너레이터 객체는 '이터러블' 이면서 동시에 '이터레이터' 이다.
+ 제너레이터 객체는 next메서드를 갖는 이터레이터 이지만, 이터레이터에는 없는 return, throw메서드를 갖는다.

### 제네레이터의 일시 중지와 재개
+ 일반함수처럼 한번에 코드 블록의 모든 코드를 일괄 실행하는 것이 아니라 yield표현식 까지만 실행함
+ yield키워드는 제너레이터 함수의 실행을 일시 중지시키거나 yield키워드 뒤에 오는 표현식의 평가 결과를 제너레이터 함수 호출자에게 반환한다.
+ 제너레이터 객체의 next메서드를 호출하면 yield표현식 까지 실행되고 일시중지함. 이때 ! 함수의 제어권이 호출자로 양도(yield)됨
+ 이때 제너레이터 객체의 next메서드가 value,done프로퍼티를 갖는 이터레이터 리절트 객체를 반환함. 이 객체의 value프로퍼티에는 yield표현식에서 yield된 값이 할당되고, done프로퍼티에는 
제네레이터 함수가 끝까지 실행되었는지를 나타내는 불리언 값이 할당됨!

### 제네레이터의 활용
+ 이터러블의 구현과 비동기처리로 활용한다.
+ 비동기 처리의 async/await : ES8에 도입됨. -> 프로미스 기반임.
+ async : await는 반드시 async함수 내부에서 사용해야 한다. async함수가 명시적으로 프로미스를 반환하지 않아도, 암묵적으로 반환값을 resolve하는 프로미스를 반환함.
+ await : 프로미스가 settled상태(비동기 처리가 수행된 상태)가 될 때까지 대기하다가 settled상태가 되면 프로미스가 resolve한 처리 결과를 반환함.
+ await키워드는 반드시 프로미스 앞에서 사용!!
+ 에러처리 ? 비동기 처리를 위한 콜백 패턴의 단점중 가장 심각한것은 에러처리가 곤란한것 인데,async/await는 try...catch문을 사용할 수 있기 때문에 catch(err)로 에러를 처리 할 수 있다.
+ 만약 async함수 내에서 catch문을 사용해서 에러처리를 하지 않으면 async함수는 발생한 에러를 reject하는 프로미스를 반환한다. 

---

+ 프로젝트로 노드JS로 서버를 만들고 있는데 컨트롤러에서 거의 사용하고 있는 부분이라 복습이 되었던 것 같다 !!
