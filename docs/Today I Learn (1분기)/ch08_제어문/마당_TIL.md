## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.16

**오늘 읽은 범위** : 8장 제어문

---

### 제어문이란

- 조건에 따라 코드 블록을 실행 하거나 반복 실행할 때 사용된다.
- 일반적으로 코드는 위에서 아래 방향으로 순차적으로 실행되는데, 제어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있음.

---

### 제어문의 종류

- 블록문 : 0개 이상의 문을 중괄호로 묶은 것
- 조건문 : 조건식의 평가 결과에 따라 코드 블록의 실행을 결정
  - if...else문
  - switch문
- 반복문 : 조건식의 평가결과가 참인 경우 코드 블록을 실행
  - for문
  - while문
- break문 : 레이블문, 반복문 또는 switch문의 코드 블록을 탈출함
- continue문 : 반복문의 코드 블록 실행을 현 지점에서 중단하고 반복문의 증감식으로 실행 흐름을 이동시킨다.

---

### 단락의 소제목

---

### 단어장 🔖

```

```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

전에 자바스크립트에서 switch문은 안쓰는게 좋다고 한 글을 봤는데, 그 이유와 대체 방법입니다.

- switch문 사용을 추천하지 않는 이유

  - 자바스크립트는 오브젝트의 자유도가 높기 때문에, 굳이 switch문을 사용하지 않아도 자바스크립트에서는 if문으로 같은 내용을 표현할 수 있다.
  - 코드가 길어져 가독성이 떨어진다.

- switch문을 if문으로 더 간결하게 작성하는법 [출처](https://learnjs.vlpt.us/useful/05-smarter-conditions.html)

```jsx
function getSound(animal) {
  switch (animal) {
    case "개":
      return "멍멍!";
    case "고양이":
      return "야옹~";
    case "참새":
      return "짹짹";
    case "비둘기":
      return "구구 구 구";
    default:
      return "...?";
  }
}

console.log(getSound("개")); // 멍멍!
console.log(getSound("비둘기")); // 구구 구 구
```

```jsx
function getSound(animal) {
  const sounds = {
    개: "멍멍!",
    고양이: "야옹~",
    참새: "짹짹",
    비둘기: "구구 구 구",
  };
  return sounds[animal] || "...?";
}

console.log(getSound("개")); // 멍멍!
console.log(getSound("비둘기")); // 구구 구 구
```

마찬가지로, if-else if - else문 역시 가능하다면 로직을 재점검하고 꼭 필요한지 확인할 필요가 있습니다. 자세한 내용은 해당 유튜브 참고
https://youtu.be/EumXak7TyQ0

---
