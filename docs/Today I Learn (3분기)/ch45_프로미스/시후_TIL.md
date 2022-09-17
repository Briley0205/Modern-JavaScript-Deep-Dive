## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.13

**오늘 읽은 범위** : 45장 프로미스

### 비동기 처리 패턴 프로미스 📑

- 콜백 패턴은 코의 처리 결과를 외부로 반환하는 데 한계가 있다.
- 프로미스는 ECMAScript 사양이 정의된 표준 빌트인 객체이다.
- 후속 처리 메서드로 .then, .catch, .finally가 있다.

---

### 비동기 처리 콜백 패턴의 단점

1. 비동기로 동작하는 코드가 완료되지 않아도,<br>
   기다리지 않고 바로 종료된다. ---> 기대한 대로 동작하지 않는다.

2. 에러 처리에 한계가 있다.

### fetch 함수의 프로미스 객체 반환

> fetch 함수는 HTTP 응답을 나타내는 Response 객체를 래핑한<br> 프로미스 객체를 반환한다.

```js
const response = await fetch(`/api/videos/${videoId}/comment`, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    text,
  }),
});
if (response.status === 201) {
  textarea.value = "";
  const { newCommentId, userAvatar, username, createdAt } =
    await response.json();
  addComment(text, newCommentId, userAvatar, username, createdAt);
}
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                                                                                                      |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 856 | catch 메서드를 모든 then 메서드를 호출한 이후에 호출하면<br> 비동기 처리에서 발생한 에러(rejected 상태) 뿐만 아니라<br> then 메서드 내부에서 발생한 에러까지 모두 캐치할 수 있다.                         |
|     | 또한 then 메서드에 두 번째 콜백 함수를 전달하는 것보다<br> catch 메서드를 사용하는 것이 가독성이 좋고 명확하다.<br> 따라서 에러 처리는 then 메서드에서 하지 말고<br> catch 메서드에서 하는 것을 권장한다. |
