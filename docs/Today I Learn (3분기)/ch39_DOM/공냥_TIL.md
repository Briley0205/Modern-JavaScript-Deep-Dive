# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.09.12

**오늘 읽은 범위** : <br>
39장

<br>

## ✨**39장, DOM**✨

DOM은 HTML 문서의 계층적 구조와 정보를 표현하며 이를 제어할 수 있는 API, 즉 프로퍼티와 메서드를 제공하는 트리 자료구조다.

### ➡️ 트리 자료구조

트리 자료구조는 노드들의 계층 구조로 이뤄진다. 트리 자료구조는 부모 노드와 자식 노드로 구성되어 노드 간 계층적 구조를 표현하는 비선형 자료구조를 말한다. 트리 자료구조는 하나의 최상위 노드에서 시작한다. 최상위 노드는 부모 노드가 없으며, 루트 노드라 한다. 루트 노드는 0개 이상의 자식 노드를 갖는다. 자식 노드가 없는 노드를 리프 노드라 한다.
<br>

🔹문서 노드<br>
문서 노드는 DOM 트리의 최상위에 존재하는 루트 노드로서 dccument 객체를 가리킨다.

🔹요소 노드<br>
요소 노드는 HTML 요소를 가리키는 객체다.

🔹어트리뷰트 노드<br>
어트리뷰트 노드는 HTML 요소의 어트리뷰트를 가리키는 객체다.

🔹텍스트 노드<br>
텍스트 노드는 HTML 요소의 텍스트를 가리키는 객체다.

<br>

### ➡️ 요소 노드 취득

HTML의 구조나 내용 또는 스타일 등을 동적으로 조작하는 먼저 요소 노드를 취득해야 한다. DOM은 요소 노드를 취득할 수 있는 다양한 메서드를 제공한다.

<br>

🔹id를 이용한 요소 노드 취득<br>
🔹태그 이름을 이용한 요소 노드 취득<br>
🔹class를 이용한 요소 노득 취득<br>
🔹CSS 선택자를 이용한 요소 노득 취득<br>
🔹Element.prototype.matches 메서드는 인수를 전달한 CSS 선택자를 통해 특정 요소 노드 취득가능한지 확인<br>
🔹HTMLCollection과 NodeList<br>

<br>

### ➡️ 노드 탐색

노드 탐색 프로퍼티는 모두 접근자 프로퍼티다. 단, 노드 탐색 프로퍼티는 setter 없이 getter만 존재하여 참조만 가능한 읽기 전용 접근자 프로퍼티다.

<br>

### ➡️ 노드 정보 취득

노드 객체에 대한 정보를 취득하려면 다음과 같은 노드 정보 프로퍼티를 사용한다. <br>

🔹Node.prototype.nodeType<br>
노드 객체의 종류. 노드 타입을 나타내는 상수를 반환.<br>

🔹Node.prototype.nodeName<br>
노드의 이름을 문자열로 반환함.<br>

🔹요소 노드의 텍스트 조작<br>

- nodeValue
- textContent

### ➡️ DOM 조작

DOM 조작은 새로운 노드를 생성하여 DOM에 추가하거나 기존 노드를 삭제 또는 교체하는 것을 말한다.<br>

🔹innerHTML<br>
setter와 getter 모두 존재하는 접근자 프로퍼티로서 요소 노드의 HTML마크업을 취득하거나 변경한다.

🔹insertAdjacentHTML<br>
기존 요소를 제거하지 않으면서 위치를 지정해 새로운 요소를 삽입한다.

🔹노드 생성과 추가

- Document.prototype.createElement메서드는 요소 노드를 생성하여 반환
- DOcument.prototype.createTextNode메서드는 텍스트 노드를 생성하여 반환한다.<br>

🔹Node.prototype.appendChild메서드는 childNode에게 인수로 전달한 노드를 appendChild 메서드를 호출한 노드 마지막 자식 노드로 추가함

🔹Node.prototype.insertBefore메서드는 첫 번째 인수로 전달 받은 노드를 두 번째 인수로 전달받은 노드 앞에 삽입함

🔹Node.prototype.cloneNode메서드는 노드의 사본을 생성하여 반환함

🔹Node.prototype.replaceChild메서드는 자신을 호출한 노드의 자식 노드를 다른 노드로 교체한다.

🔹Node.prototype.removeChild메서드는 child 매개변수에 인수로 전달한 노드를 DOM에서 삭제한다.

<br>

### ➡️ HTML 어트리뷰트

HTML 어트리뷰트의 역할은 HTML 요소의 초기 상태를 지정하는 것이다. 즉, HTML 어트리뷰트 값은 HTML 요소의 초기 상태를 의미하여 이는 변하지 않는다.

🔹어트리뷰트 노드<br>
HTML 어트리뷰트로 지정한 HTML 요소의 초기 상태는 어트리뷰트 노드에서 관리한다.

🔹DOM 프로퍼티<br>
사용자가 입력한 최신 상태는 HTML 어트리뷰트에 대응하는 요소 노드의 DOM 프로퍼티가 관리한다. DOM 프로퍼티는 사용자의 입력에 의한 상태 변화에 반응하여 언제나 최신 상태를 유지한다.

🔹인라인 스타일 조작<br>
HTMLelement.prototype.style 프로퍼티는 setter와 getter 모두 존재하는 접근자 프로퍼티로서 요소 노드의 인라인 스타일을 취득하거나 추가 또는 변경한다.

🔹클래스 조작<br>
.으로 시작하는 클래스 선택자를 사용하여 CSS class를 미리 정의한 다음, HTML 요소의 class 어트리뷰트 값을 변경하여 HTML 요소의 스타일을 변경할 수 있다.

- className
- classList
