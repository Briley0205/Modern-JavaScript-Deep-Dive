## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.26

**오늘 읽은 범위** : 13장 스코프

### 스코프

스코프는 JS를 포함한 모든 프로그래밍 언어의 기본적이며 중요한 개념

모든식별자는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효범위가 결정된다.
스코프는 식별자가 유효한 범위를 뜻한다.

```js
var env = 'global';

function example() {
  var env = 'local';
  console.log(env); // local
}

console.log(env); // global
```

만약 스코프라는 개념이없다면 같은 이름을 가진 변수는 충돌을 일으키므로 프로그램 전체에서 하나밖에 사용할 수 밖에 없을것이다.

렉시컬환경은 다음 챕터에서 자세하게 다룰 예정
