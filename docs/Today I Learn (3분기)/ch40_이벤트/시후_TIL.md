## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.05 - 06

**오늘 읽은 범위** : 40장 이벤트

### 이벤트 드리븐 프로그래밍 📑

- 프로그램을 이벤트 중심으로 제어한다.
- 이벤트 핸들러는 공통적으로 이벤트 객체를 생성하고 그 인수로 전달한다.

---

### 이벤트 핸들러 방식

1. 어트리뷰트 방식

```html
<button onclick="sayHi('Yun')">Click me!</button>
<script>
  function sayHi(name) {
    console.log(`Hi ${name}`);
  }
</script>
```

2. 프로퍼티 방식

```js
const button = document.querySelector("button");

function clickHandler() {
  console.log("You clicked me!");
}

button.onclick = function () {
  console.log("You clicked me!");
};
button.addEventListener("click", clickHandler);
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                   |
| --- | ---------------------------------------------------------------------------------------------------------------------- |
| 772 | 이벤트 객체 중 일부는 사용자의 행위에 의해 생성된 것이고 일부는<br> 자바스크립트 코드에 의해 인위적으로 생성된 것이다. |
| 782 | 이벤트는 이벤트를 발생시킨 이벤트 타깃은 물론<br> 상위 DOM 요소에서도 캐치할 수 있다.                                  |

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
이벤트 위임:
  여러 개의 하위 DOM 요소에 이벤트 핸들러를 등록하는 대신
  하나의 상위 DOM 요소에 이벤트 핸들러를 등록하는 방법을 말한다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
그냥 자연스럽게 사용하던 것들을 글로 마주하니 새롭다.
하지만 이런 건 역시 실전이 최고인 듯 하다.
```
