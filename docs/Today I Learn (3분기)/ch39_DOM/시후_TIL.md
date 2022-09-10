## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.01 - 04

**오늘 읽은 범위** : 39장 DOM

### Document Object Model 📑

- 노드 객체들로 구성된 트리 자료 구조
- 부모 노드와 자식 노드들의 계층 구조와 정보를 표현한다.
- API를 통해 노드들을 제어할 수 있다.

---

### 4가지 노드 타입

```js
1. 문서 노드 : DOM트리 최상위에 존재하는 루트 노드.
 유일한 Document 객체를 가리킨다.

2. 요소 노드 : 요소 간의 중첩으로 계층적 구조를 이루는 노드

3. 어트리뷰트 노드 : HTML 요소의 어트리뷰트

4. 텍스트 노드 : DOM트리의 최종단 노드.
 요소 노드만이 부모가 될 수 있다.
```

### 요소 노드 취득법

> 요소 노드를 취득할 수 있는 메서드

```HTML
<li class="liClass" id="liId"></li>
```

```js
Document.prototype.getElementId("liId");
Document.prototype.getElementsByTagName("li");
Document.prototype.getElementsByClassName("liClass");
Document.prototype.querySelector("li");
```

### 요소 노드의 족보 탐색

> 요소 노드를 취득하여 부모/형제/자식 요소의<br> 정보를 가져와야 할 때가 있다.

```js
const target = srcElement.parentNode.dataset.id;
```

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
공백 텍스트 노드:
  HTML요소 사이의 스페이스, 탭, 줄바꿈 등의 공백 문자가
  생성하는 텍스트 노드이다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
요소 노드 또한 프로토타입을 통한 메서드 상속으로
다양한 특성을 가진다는 점이 가장 흥미로웠다.
이제껏 아무런 의문도 가지지 않은 채 사용했던 기능들을
다시보게 되었다.
```
