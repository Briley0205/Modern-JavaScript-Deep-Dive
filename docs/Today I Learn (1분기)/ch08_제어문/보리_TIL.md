## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.16

**오늘 읽은 범위** : 8장 제어문
+ 조건에 따라 코드를 실행하거나 반복할때 사용합니다.

### 블록문
+ 0개 이상의 문을 중괄호로 묶은 것, 코드블록 또는 블록이라고 부릅니다.
```js
{ var koo = 10; }
```

### 조건문
+ 주어진 조건식에 평가결과에 따라 코드블록의 실행을 결정합니다.
+ if else와 switch가 있습니다.
```js
if(조건식){}else{};
if(조건식){} else if(조건식2){} else {};

switch(표현식){
  case 표현식1:
    switch 문의 표현식과 표현식1이 일치하면 실행될문;
    break;
  default:
    switch 문의 표현식과 일치하는 case문이 없을 때 실행될 문;
}
```

### 반복문
+ for : 조건식이 거짓으로 평가될 때까지 코드블록을 반복실행
+ while : 주어진 조건식의 평가결과가 true면 코드블록을 계속해서 반복실행
+ do...while : 코드블록을 일단 먼저 실행하고 조건식을 평가,무조건 한번 이상 실행됩니다.

### break문
+ 레이블문, 반복문 또는 switch문의 코드 블록을 탈출합니다.

### continue문
+ 반복문의 코드 블록 실행을 현지점에서 중단, 반복문의 증감식으로 실행 흐름을 이동시킵니다.
+ break문과 달리 반복문을 탈출하지는 않습니다.

---
#### if else -> '삼항연산자'로 가능!
```js
var x = 4;
var result = x % 2 ? '홀수' : '짝수';
console.log(result); //짝수, 이렇게 사용하면 더 깔끔하다!
//혹시 내용이 복잡하거나 여러줄의 문이 필요하면 if else사용하는 편이 가독성이 좋다.
```

### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
```
반복문에 대해 더 공부를 해봐야 겠습니다..! 왜그런지는 모르겠지만, 제가 만들었던 웹이나 앱들은 (물론 많지는 않지만...)
if else대신에 삼항연산자를 많이 썼고, 반복문은 거의 안썼는데,, 그래서 쓰는 방법을 잘 몰랐었는데, 예제를 통해 한번씩 만들어 봐야겠습니다..!

```


---

### 다른 분이 작성하신 TIL에 대한 소감
```

```
