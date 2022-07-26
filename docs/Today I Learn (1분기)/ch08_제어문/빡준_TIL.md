## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.16

**오늘 읽은 범위** : 8장 8.1 ~ 8.5

### 코드 흐름을 제어하는 댐, 제어문 📑

- 제어문은 조건식을 확인함으로서, 프로그램의 흐름을 제어한다.
- 조건문은 else if가 일반적이나, 복잡한 조건문은 switch를 사용할 수 있다.
- break, continue 문을 통해 제어문을 빠져나오거나, 제어문 내의 흐름을 바꿀 수 있다.

---

### 책속 한구절 보관함 📖

| p   | text                                                                                                                                                                                                                           |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 93  | 제어문을 사용하면 코드의 흐름을 인위적으로 제어할 수 있다.                                                                                                                                                                 

### 단어장 🔖

제어문(control flow statement) :

> 조건에 따라 코드블록을 실행하거나 반복 실행할 때 사용한다.

```js
if (data: 조건식) {
    console.log('data is ready');
}
조건식과 블록문(코드 블록) 으로 이루어진 조건문으로,
조건식이 참이면 코드 블록이 실행된다.

const Data = data ? 'data is ready' : 'loading...'

또한 대부분의 if ...else 문은 삼항 조건 연산자로 바꿀 수 있다.
```

> 복수의 `if` 조건문은 `switch`문으로 바꿀 수 있다.

```js
const header = document.getElementById("header")
const textInput = document.getElementById("text").value;
switch (textInput) {
    case "red":
        header.style.color = "red";
        break;
    case "blue":
        header.style.color = "blue";
        break;
    case "green":
        header.style.color = "green";
        break;
    default:
        header.style.color = "black";
}

위 조건문은 input에 입력한 값에 따라 header색깔을 바꾼다.
이 조건문을 if ...else 로 바꾸면 이렇게 할 수 있다.

if (textInput === "red") {
    header.style.color = "red";
} else if (textInput === "blue") {
    header.style.color = "blue";
} else if (textInput === "green") {
    header.style.color = "green";
} else {
    header.style.color = "black";
}
```

> while 문과 do ...while 문은 조건식의 평가 시점이 다르다.

```js
// 조건식 평가 후 실행
let age = 5
while (age < 10) {
    console.log('your age is less than 10');
    age++;
}
document.write('you are now over 10');

|| 이렇게 바꿔쓸 수 있다.

// 실행 후 조건식 평가
do {
    console.log('your age is less than 10');
    age++;
} while (age < 10);
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
antd Form 데이터의 key값이 변경될때 if else 혹은 삼항연산자로 데이터를 핸들링한 경험은 많았지만, switch 를 사용했더라면 더욱 코드가 알아보기도 쉬웠을것같다. 클린한 코드르 작성하는 법을 까먹고있던것같아 아쉽다.
```

---

### 다른 분이 작성하신 TIL에 대한 소감
