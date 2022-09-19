## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.17

**오늘 읽은 범위** : 46장 제너레이터와 async / await

### 동기 / 비동기 처리 📑

- ES8 이전에 제너레이터를 통해 동기 처리를 구현했다.
- 하지만 장황한 코드로 인해 가독성이 떨어졌다.
- 때문에 간단하고 가독성 좋은 async / await 이 도입되었다.

---

### async 함수와 await 키워드

> await 키워드는 반드시 async 함수 내부에서 사용해야 한다.

```js
const postLogin = async (req, res) => {
  const userExists = await User.findOne({ email, socialOnly: false });
  if (!userExists) {
    return res.status(400).render("login", {
      pageTitle,
      errorMessage: "An account with this email does not exists.",
    });
  }
};
```

### 책속 한구절 보관함 📖

| p   | text                                                                                                                          |
| --- | ----------------------------------------------------------------------------------------------------------------------------- |
| 881 | async 함수가 명시적으로 프로미스를 반환하지 않더라도<br> async 함수는 암묵적으로 반환값을 resolve하는 프로미스를 반환한다.    |
| 882 | await 키워드는 반드시 프로미스 앞에서 사용해야 한다.                                                                          |
| 884 | async 함수 내에서 catch 문을 사용해서 에러 처리를 하지 않으면<br> async 함수는 발생한 에러를 reject 하는 프로미스를 반환한다. |

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
제너레이터:
  코드 블록의 실행을 일시 중지했다가 필요한 시점에 재개할 수
  있는 특수한 함수다.
```
