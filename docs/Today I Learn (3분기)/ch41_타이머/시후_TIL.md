## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.07

**오늘 읽은 범위** : 41장 타이머

### 싱글 스레드 비동기 처리 방식 타이머 📑

- 일정 시간이 경과된 이후의 함수 호출 방법

---

### 디바운스 / 스로틀

> 디바운스<br> 짧은 시간 간격으로 발생하는 이벤트를 그룹화해서<br> 마지막에 한 번만 이벤트 핸들러가 호출되도록 한다.

```js
const input = document.querySelector("input");
const msg = document.querySelector(".msg");
const debounce = (callback, delay) => {
  let timerId;
  return (event) => {
    if (timerId) clearTimeout(timerId);
    timerId = setTimeout(callback, delay, event);
  };
};
input.oninput = debounce((e) => {
  msg.textContent = e.target.value;
}, 300);
```

> 스로틀<br> 짧은 시간 간격으로 이벤트가 연속해서 발생하는 이벤트를 그룹화해서<br> 일정 시간 단위로 이켄트 핸들러가 호출되도록 호출 주기를 만든다.

```js
const input = document.querySelector("input");
const throttle = (callback, delay) => {
  let timerId;
  return (event) => {
    if (timerId) return;
    timerId = setTimeout(
      () => {
        callback(event);
        timerId = null;
      },
      delay,
      event
    );
  };
};
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                                                                                                                                            |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 801 | 자바스크립트 엔진은 단 하나의 실행 컨텍스트 스택을 갖기 때문에<br> 두 가지 이상의 테스크를 동시에 실행할 수 없다.<br> 즉, 자바스크립트 엔진은 싱글 스레드로 동작한다.<br> 이런 이유로 setTimeout과 setInterval은 비동기 처리 방식으로 동작한다. |

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
호출 스케줄링:
  일정 시간이 경과된 이후에 호출되도록 함수 호출을 예약하는 것.

```
