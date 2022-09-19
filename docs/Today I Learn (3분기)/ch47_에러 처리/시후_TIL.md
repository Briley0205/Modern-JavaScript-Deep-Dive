## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.17

**오늘 읽은 범위** : 47장 에러 처리

### 프로그램을 스무스하게 진행시키기 위한 방법 📑

#### +간결한 세 줄 요약

---

### 에러 처리가 필요한 이유 ?

> 에러나 에외적인 상황에 대처하지 않으면<br> 프로그램이 강제 종료되기 때문.

1. try, catch, finally

```js
export const getAuth = (req, res) => {
  try {
    return res.render("auth", { pageTitle: "Authorize" });
  } catch (err) {
    console.log(err.message);
  } finally {
    // 에러와 상관없이 한 번 실행되는 코드
  }
};
```

2. Error 객체

```js
const err = new Error("invalid input");
```

3. throw 문

```js
try {
  throw new Error("invalid code");
} catch (error) {
  console.log(error);
}
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                                   |
| --- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 887 | 우리가 작성한 코드에서는 언제나 에러나 예외적인 상황이 발생할 수<br> 있다는 것을 전제하고 이에 대응하는 코드를 작성하는 것이 중요하다. |
