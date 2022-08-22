## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.20

**오늘 읽은 범위** : 24장 

### 클로저 ?

+ JS고유의 개념이아님. 함수를 입급객체로 취급하는 함수형 프로그래밍 언어에서 사용되는 중요한 특성임.

### 함수 객체의 내부 슬롯 [[Environment]]
+ 함수 정의가 평가되어 함수객체를 생성할 때 자신의 정의된 환경에 의해 결정된 상위 스코프의 참조를 함수 객체 자신의 내부슬롯에 저장함.
+ 함수객체의 [[Environment]] 에 저장된 현재 실행중인 실행 컨텍스트의 렉시컬 환경의 참조가 바로 상위 스코프임.
+ 또한 자신이 호출되었을 때 생성될 함수 렉시컬 환경의 외부렉시컬 환경에 대한 참조에 저장될 참조값.
+ 함수 객체는 [[Environment]] 에 저장한 렉시컬 환경의 참조, 죽 상위 스코프를 자신이 존재하는 한 기억함.

### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
```js
클로저는 폐쇄된 느낌. 즉, 내부함수와 외부함수에 상태가 함께 묶여있는 느낌인것 같다.
내부에서 외부로는 참조가능, 외부에서는 접근불가하다.
엄밀히 말하면 내부에서 외부를 다 참조할 수 있다고 해서 클로저라고는 하지 않는다.
중첩된 함수에서 내부에 있는 함수와, 외부에 있는 함수의 상태, 렉시컬 환경이 저장되어 있기 떄문에..
즉, 데이터에 접근할 수 있는 것을 클로저 라고 한다.
function fruit(){
  const x = 1;
  function apple(){
    console.log(`apple is fruit: ${x}`);
    }
    apple();
}
fruit(); 
//예시가 좀 이상하긴한데.. 여기서 apple안에 x가 외부의, 즉fruit의 x에 접근이 가능함.
//그래서 fruit내부에서 하수를 선언하고 바로 호출하면 1이 출력됨
//내부 함수는 외부함수에 접근이 가능하기 때문에 apple is fruit: 1 이출력됨

클로저활용 .. mdn을 참고해 봤는데.
function counter(){
  let count = 0;
   function increment(){
    count++;
    console.log(count);
   }
   return increment;
 }
 const increment = counter();
 increment(); //1
 increment(); //2
 호출할 수록 count++이 되어 1씩 올라간다.
 이처럼 클로저를 이용해서 함수로 은닉하고자 하는 데이터 상태를 감추고, 퍼블릭함수만을 통해서 
 내부 데이터 조작을 할 수 있게 만들어 줄 수 있음.
 하지만 요즘에는 클로저 대신 class를 사용함.
 
 위의 클로저를 class로 바꿔보자면
 class Counter(){
  #count = 0;
  increment(){
    this.#count++;
    console.log(this.#count);
  }
}
const counter = new Counter();
counter.increment(); 
// 이런 형태로 class를 작성할 수 있음.
지난번에 공부했던 실행컨텍스만 잘 이해하면 크게 어렵지 않은 것같다..!
```
