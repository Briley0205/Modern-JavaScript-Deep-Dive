# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : 2022.07.27

**오늘 읽은 범위** : 14장, 전역 변수의 문제점

## ✨**14장 전역 변수의 문제점**✨

### ➡️**변수의 생명주기**

변수는 자신이 선언된 위치에서 생성되고 소멸한다.
전역 변수의 생명 주기는 애플리케이션의 생명 주기와 같다.
반면 지역 변수는 지역 변수가 위치한 함수가 종료하면 소멸된다. 즉 지역 변수의 생명 주기는 함수의 생명 주기와 같다.

함수 내부에서 선언된 지역 변수는 함수가 호출된 직후 함수 내부 코드가 한 줄씩 순차적으로 실행되기 이전, 자바스크립트 엔진에 의해 먼저 실행된다.

<br>

### ➡️**전역 변수의 문제점**

🔹암묵적 결합🔹 <br>
전역 변수 특성상 모든 코드가 전역 변수를 참조하고 변경할 수 있다. 이는 암묵적 결합을 허용하는 것이다. 변수 유효 범위가 크면 클수록 코드 가독성은 나빠지고, 의도치 않게 상태가 변경될 수 있다.

🔹긴 생명 주기🔹 <br>
전역 변수는 생명 주기가 길다. 때문에 메모리 리소스도 오랜 기간 소비하게 된다. 생명 주기가 긴 만큼 전역 변수의 상태 변경할 수 있는 여지가 더 많아진다. 이는 코드의 오류 확률을 높인다. var 키워드를 사용할 경우에는 중복 선언이 가능하다는 특성 때문에 의도치 않은 재할당이 일어날 위험성이 높다.

🔹스코프 체인 상 종점에 존재🔹 <br>
전역 변수는 스코프 체인에서 제일 마지막에 검색된다. 즉 전역 변수 검색 속도가 가장 느리다. 속도 차이가 크지 않다 해도 속도 차이는 분명히 있다.

🔹네임스페이스 오염🔹 <br>
자바스크립트는 파일이 분리되어 있어도 하나의 전역 스코프를 공유한다. 때문에 다른 파일 내에서 동일한 이름으로 명명된 전역 변수, 전역 함수가 동일한 스코프 내에 있다면 오류가 일어나거나 예상치 못한 결과를 가지고 올 위험성이 높다.

<br>

### ➡️**전역 변수 사용을 억제하는 방법**

전역 변수는 무분별하게 사용하면 안 된다. 반드시 전역 변수를 사용해야 할 이유를 찾지 못한다면 지역 변수를 사용해라. 변수 스코프는 좁으면 좁을수록 좋다. 억제하는 방법은 아래와 같다.

🔹즉시 실행 함수🔹 <br>
함수 정의 동시 호출되는 즉시 단 한 번만 실행되는 함수.<BR>
`(function newFunc(){var new = 5;}());` <br>
모든 코드를 즉시 실행 함수로 감싸면 모든 변수는 즉시 실행 함수 내의 지역 변수가 된다. 이 방법은 라이브러리 등에 자주 사용된다.

🔹네임스페이스 객체🔹 <br>
전역에 네임스페이스 포지션을 담당할 객체를 생성하고, 전역 변수처럼 사용하고자 하는 변수를 프로퍼티로 추가한다.

```javascript
let player = {}; //전역 스페이스 네임 객체
player.name = "john";
console.log(player.name); //john
```

🔹모듈 패턴🔹 <br>
클래스를 모방해 관련 있는 변수와 함수를 모아 즉시 실행 함수로 감싸 하나의 모듈을 만든다. 전역 변수 억제 뿐만 아니라 캡슐화까지 구현 가능하다.

전역 네임스페이스 오염을 막는 기능 + 한정적이긴 하나 정보 은닉을 구현하는 데에 사용할 수 있다.

```javascript
let Counter = (function () {
  //private 변수
  let num = 1;

  //외부로 공개할 데이터, 메서드를 프로퍼티로 추가한 객체를 반환
  return {
    increase() {
      return ++num;
    },
    decrease() {
      return --num;
    },
  };
})();

console.log(Counter.num); // undefined, private 변수이므로 노출되지 않는다.
console.log(Counter.increase()); // 2
console.log(Counter.decrease()); // 1
```

외부로 노출하고 싶지 않은 변수 및 함수는 반환하는 객체에 추가하지 않으면 외부에서 접근이 안 되는 프라이빗 멤버가 된다.

<br>

### ➡️**ES6 모듈**

ES6 모듈 사용시 전역 변수를 사용할 수 없다. 파일 자체의 독자적 모듈 스코프를 제공한다.

모던브라우저에서 사용 가능하며, script 태그에 `type = "module"`속성을 추가하면 로드된 자바스크립트 파일은 모듈로서 작동한다. 확장자는 `mjs`를 권장한다.

다만 트랜스파일링이나 번들링이 필요하기에 아직까지는 ES6 모듈 기능보다는 Webpack 등 모듈 번들러를 사용하는 게 일반적이다.

<br>

## 📝 오늘의 책갈피

➖

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
Webpack:
모듈 번들링.
html 파일에 들어가는 자바스크립트 파일들을 하나의 자바스크립트 파일로 만들어주는 방식을 모듈 번들링이라고 한다.

파일 컴파일 시 여러 모듈들의 파일을 읽어오는 데에 시간이 오래 걸리는데, 이 문제를 해결하기 위해 여러 파일을 하나의 파일로 번들링을 한다.
즉, 하나의 파일로 만듦으로써 웹페이지 성능을 최적화하는 것이다.

```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
class를 사용할 때 프라이빗 필드를 만들어본 적이 있었는데, 모듈 패턴화로 함수를 모아서 + 즉시실행함수 만들 때 프라이빗 변수를 만들어줄 수 있다는 사실을 오늘 처음 알았다. 언어는 알면 알수록 알아야 할 게 많구나 싶다.

변수에게도 생명 주기가 있다는 건 생각해본 적도 없었고 오늘 처음 알았다. 이를 유의해서 전역 변수는 정말 필요할 때만 사용하도록 해야겠다.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
-Babel 사용법, Webpack을 어떻게 쓰는지 (사용법은 찾아봤지만 아직 내가 이것부터 해야 할 레벨은 아닌 듯하다)

-전역 변수를 꼭 써야하는 경우가 있다면 그건 어떤 경우일까?

```
