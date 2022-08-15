## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.15

**오늘 읽은 범위** : 22장 this

## This

### This 키워드

- 자신이 속한 객체를 가리키는 식별자를 참조
    - 객체 리터럴
        - 자신이 속한 객체를 재귀적으로 참조하는 방식은 일반적이지도 바람직하지도 않다.
    
    ```jsx
    const circle = {
      // 프로퍼티: 객체 고유의 상태 데이터
      radius: 5,
      // 메서드: 상태 데이터를 참조하고 조작하는 동작
      getDiameter() {
        // 이 메서드가 자신이 속한 객체의 프로퍼티나 다른 메서드를 참조하려면
        // 자신이 속한 객체인 circle을 참조할 수 있어야 한다.
        return 2 * circle.radius;
      }
    };
    
    console.log(circle.getDiameter()); // 10
    ```
    
    - 생성자 함수
        - 생성자 함수를 정의하는 시점에는 인스턴스 생성이 되지 않았기에 인스턴스를 가키리는 식별자를 알 수 없다.
    
    ```jsx
    function Circle(radius) {
      // 이 시점에는 생성자 함수 자신이 생성할 인스턴스를 가리키는 식별자를 알 수 없다.
      ????.radius = radius;
    }
    
    Circle.prototype.getDiameter = function () {
      // 이 시점에는 생성자 함수 자신이 생성할 인스턴스를 가리키는 식별자를 알 수 없다.
      return 2 * ????.radius;
    };
    
    // 생성자 함수로 인스턴스를 생성하려면 먼저 생성자 함수를 정의해야 한다.
    const circle = new Circle(5);
    ```
    
- 위 예제들과 같은 상황에서 자신이 속한 객체를 가리키는 식별자로서 제공된 키워드가 this 이다.
    - 자신이 속한 객체 혹은 자신이 생성할 인스턴스를 가리키는 자기 참조 변수이다.
    - this 가 가리키는 값은 함수 호출 방식에 의해 동적으로 결정된다.
    - this 는 객체의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수이므로 객체의 메서드 내부 또는 생성자 함수 내부에서만 의미가 있다.
    

### 함수 호출 방식과 this 바인딩

- 위에서 언급 했듯이 this 바인딩은 함수 호출 방식에 다라 동적으로 결정된다.
    1. 일반 함수 호출
    2. 메서드 호출
    3. 생성자 함수 호출
    4. Function.prototype.apply/call/bind 메서드에 의한 간접호출
    
    ```jsx
    // this 바인딩은 함수 호출 방식에 따라 동적으로 결정된다.
    const foo = function () {
      console.dir(this);
    };
    
    // 동일한 함수도 다양한 방식으로 호출할 수 있다.
    
    // 1. 일반 함수 호출
    // foo 함수를 일반적인 방식으로 호출
    // foo 함수 내부의 this는 전역 객체 window를 가리킨다.
    foo(); // window
    
    // 2. 메서드 호출
    // foo 함수를 프로퍼티 값으로 할당하여 호출
    // foo 함수 내부의 this는 메서드를 호출한 객체 obj를 가리킨다.
    const obj = { foo };
    obj.foo(); // obj
    
    // 3. 생성자 함수 호출
    // foo 함수를 new 연산자와 함께 생성자 함수로 호출
    // foo 함수 내부의 this는 생성자 함수가 생성한 인스턴스를 가리킨다.
    new foo(); // foo {}
    
    // 4. Function.prototype.apply/call/bind 메서드에 의한 간접 호출
    // foo 함수 내부의 this는 인수에 의해 결정된다.
    const bar = { name: 'bar' };
    
    foo.call(bar);   // bar
    foo.apply(bar);  // bar
    foo.bind(bar)(); // bar
    ```
