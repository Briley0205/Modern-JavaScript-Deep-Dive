## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.31

**오늘 읽은 범위** : 38장 브라우저의 렌더링 과정

### 시각화하여 나타내기까지의 과정 📑

- HTML, CSS, JS를 순서대로 파싱하여 해석한다.
- DOM과 CSSOM를 렌더 트리로 결합한다.
- 실행 시 자바스크립트가 DOM api 를 사용하여<br> DOM과 CSSOM을 변경할 수 있다.

---

### 렌더링 과정

```js
1. 브라우저는 HTML, CSS, JS, img, font 파일 등 렌더링에 필요한
 리소스를 요청하고 서버로부터 응답을 받는다.

2. 브라우저의 렌더링 엔진은 서버로부터 응답된 HTML, CSS 를
 파싱하여 DOM, CSSOM 을 생성하고 이들을 결합하여
 렌더 트리를 생성한다.

3. 브라우저의 자바스크립트 엔진은 서버로부터 응답된 자바스크립트를
 파싱하여 AST (추상적 구문 트리)를 생성하고 바이트코드로 변환하여
 실행한다. 이때 자바스크립트는 DOM API 를 통해 DOM 이나 CSSOM 을
 변경할 수 있다. 변경된 DOM 과 CSSOM 은 다시 렌더 트리로 결합된다.

4. 렌더 트리를 기반으로 HTML 요소의 레이아웃(위치와 크기)을
 계산하고 브라우저 화면에 HTML 요소를 페인팅한다.
```

> 레이아웃 계산과 페인팅이 재차 실행되는 경우

```js
1. 자바스크립트에 의한 노드 추가 또는 삭제
2. 브라우저 창의 리사이징에 의한 viewport 크기 변경
3. HTML 요소의 레이아웃에 변경을 발생시키는 등의 스타일 변경
 (widht/height, margin, padding 등)
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                                                                                                                                     |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 662 | 루트 요청에는 명확히 리소스를 요청하는 내용이 없지만 일반적으로<br> 서버는 루트 요청에 대해 암묵적으로 index.html을 응답하도록<br> 기본 설정되어 있다. 즉, https://poiemaweb.com은<br> https://poiemaweb.com/index.html과 같은 요청이다. |
| 669 | 레이아웃 계상과 페인팅을 다시 실행하는 리렌더링은 비용이 많이 드는,<br> 즉 성능에 악영항을 주는 작업이다. 따라서 가급적 리런더링이 빈번하게 <br> 발생하지 않도록 주의할 필요가 있다.                                                     |

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
파싱 (구문 분석):
  프로그래밍 언어의 문법에 맞게 작성된 텍스트 문서를 읽어 들여
  실행하기 위해 텍스트 문서의 문자열을 토큰으로 분해하고,
  토큰에 문법적 의미와 구조를 반영하여 트리 구조의 자료구조인
  파스 트리를 생성하는 일련의 과정을 말한다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
깃헙에서 페이지를 렌더링할 때 또한 루트("/")요청 시
자동으로 index파일을 찾는 이유도 이것이 아닐까 싶다.
```

> https://poiemaweb.com === https://poiemaweb.com/index.html

```
"불필요한 리렌더링은 성능을 떨어뜨린다" 는 말에
전적으로 동의한다. 컴포넌트 중 극히 일부가 변경되었다고
전체를 갈아엎고 다시 그리는 것은 대단히 비효율적인 행동이니까.

이런 합리적이지 않은 과다 리렌더링을 방지하기 위해
React에서는 remember 메서드를 제공하고 있다.
내용이 변경된 요소만 다시 그리고, 나머지는 그대로 냅두는 기능이다.
```
