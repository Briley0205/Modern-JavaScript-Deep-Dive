# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.09.05

**오늘 읽은 범위** : <br>
35장

<br>

## ✨**34장, 스프레드 문법**✨

- 왠만한 좋은 것들은 es6에서 생긴것 같다.
- 스프레드 문법 또한 그렇다.
- 무척 간단하지만 무지성으로 쓰면 문법오류가 나니 조심.

- 스프레드 문법 : =전개문법, 하나로 뭉처있는 여러 값들의 집합을 펼쳐서 개별적인 값들의 목록으로 만든다.

- 스프레드 문법의 대상 : 이터러블. 아마도 초보때 많이 보는 오류중 하나가 얘는 이터러블이 아닙니다하는 에러일 것이다. 이터러블의 개념을 34장에서 배우고 35장을 읽으니 이해가 잘 되는 것 같다.

- 스프레드 문법의 결과 : 값들의 목록. 값이 아니다. === 스프레드 문법은 연산자가 아니다. === 그래서 스프레드 문법은 변수에 할당 할 수 없다.

- 스프레드 문법이 사용가능한 문맥

  - 함수호출물의 인수목록 : 함수에 인수 여러개를 보내고 싶을때 그게 배열형태라면 ...로 뜯어서 보낼 수 있다.

  - 배열리터럴의 요소목록 : 2개 이상의 배열을 합치거나 해서 1개의 배열리터럴을 생성하고 싶을때 concat보다 가독성이 좋고 간편하다. 배열 중간에 뭘 넣거나 자르거나 할때도 결과값을 다 뜯어서 1층에 갖다주기에 편하고 좋다.

  - 객체리터럴의 프로퍼티 목록 : 객체에도 스프레드를 사용할 수 있다! 기존에는 객체 두개를 합치기 위해 Object.assign을 사용해야 하는데 이를 스프레드로 편하게 대체할 수 있게 되었다.

## 후기

- 너무 짧긴 하다...
- 비가 온다🌧️☂️
