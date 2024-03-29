## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.09.08 - 11

### 40장 이벤트 📑

---
### 이벤트 드리븐 프로그래밍
처리해앟ㄹ 특정 사건이 발생하면 브라우저는 이를 감지하여 이벤트를 발생시킨다.
- 이벤트 핸들러 : 이벤트가 밸생했을 때 호출될 함수
- 이벤트 핸들러 등록 : 이벤트가 발생했을 때 브라우저에게 이벤트 핸들러의 호출을 위임

이벤트와 그에 대응하는 함수를 통해 사용자와 애플리케이션은 상호작용을 한다. 프로그램의 흐름을 이벤트 중심으로 제어하는 프로그래밍 방식을 이벤트 드리븐 프로그래밍이라 한다.

---
### 이벤트 타입
이벤트의 종류를 나타내는 문자열. 마우스 이벤트, 키보드 이벤트, 포커스 이벤트, 폼 이벤트, 값 변경 이벤트, DOM 뮤테이션 이벤트, 뷰 이벤트, 리소스 이벤트 등이 있다.

---
### 이벤트 핸들러 등록
1. 이벤트 핸들러 어트리뷰트 방식<br>
HTML 요소의 어트리뷰트 중 이벤트에 대응하는 이벤트 핸들러 어트리뷰트가 있다. on 접두사와 이벤트의 종류를 나타내는 이벤트 타입으로 이루어져있다.
2. 이벤트 핸들러 프로퍼티 방식<br>
Window 객체와 Document, HTMLElement 타입의 DOM 노드 객체는 이벤트에 대응하는 핸들러 프로퍼티를 가지고 잇다. 마찬가지로 on 접두사와 이벤트 종류를 나타내는 이벤트 타입으로 이루어져 있다.
3. addEventListener<br>
DOM Level 2에서 도입된 내용으로 EventTarget.prototype.addEventListener 메서드를 사용하여 등록하는 방식이다.

---
### 이벤트 핸들러 제가
addEventListener 메서드로 등록한 이벤트 핸들럴르 제거하려면 EventTarget.prototype.removeEventListener 메서드를 사용한다. 이때 addEventListener 메서드에 전달한 인수와 동일한 인수를 사용해야한다.

---
### 이벤트 객체
이벤트가 발생하면 이벤트에 관련한 다양한 정보를 담고 있는 이벤트 객체가 동적으로 생성. 이는 이벤트 핸들러의 첫 번째 인수로 전달된다.

---
### 이벤트 전파
DOM 트리 상에 존재하는 DOM 요소 노드에서 발생한 이벤트는 DOM 트리를 통해 전파되고 이를 이벤트 전파(event propagation)라고 한다.

- 캡처링 단계 : 이벤트가 상위요소에서 하위 요소 방향으로 전파
- 타깃 단계 : 이벤트가 이벤트 타깃에 도달
- 버블링 단계 : 이벤트가 하위요소에서 상위 요소 방향으로 전파
 
---
### 이벤트 위임
이벤트 위임은 여러 개의 하위 DOM 요소에 각각 이벤트 핸들러를 등록하는 대신 하나의 상위 DOM 요소에 이벤트 핸들러를 등록하는 방법을 말한다.

상위 요소에 이벤트 핸들러를 등록하기 때문에 이벤트 타깃, 즉 이벤트를 실제로 발생시킨 DOM 요소가 개발자가 기다한 DOM 요소가 아닐 수도 있다. 따라서 이벤트에 반응이 필요한 DOM요소에 한정하여 이벤트 핸들러가 실행되도록 이벤트 타깃을 검사할 필요가 있다.
 
---
### 커스텀 이벤트
이벤트가 발생하면 암묵적으로 생성되는 이벤트 객체는 발생한 이벤트의 종류에 따라 이벤트 타입이 결정된다. 하지만 Event, UIEvent, MouseEvent 같은 이벤트 생성자 함수를 호출하여 명시적으로 생성한 이벤트 객체는 임의의 이벤트 타입을 지정할 수 있다. 이처럼 개발자의 의도로 생성된 이벤트를 커스텀 이벤트라고 한다.

생성된 커스텀 이벤트 객체는 버블링되지 않으며 preventDefault 메서드로 취소할 수 없다. 즉, 커스텀 이벤트 객체는 bubbles와 cancelable 프로퍼티의 값이 false로 기본 설정된다.

---