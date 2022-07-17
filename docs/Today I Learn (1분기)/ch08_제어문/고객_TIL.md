## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.17

**오늘 읽은 범위** : 8장 제어문

### 제어문

---

### 📖 제어문

제어문은 조건에 따라 코드 블록을 실행하거나 반복실행할 때 사용한다.



---

### 📖 블록문

- 블록문은 0개 이상의 문을 중괄호로 묶은 것이다. 
- 블록문은 코드 블록 또는 블록이라고 부른다.
- 자바스크립트는 블록문을 하나의 실행 단위로 취급한다.
- 블록문은 단독으로 사용할 수도 있으나 일반적으로 제어문이나 함수를 정의할 때 사용하는 것이 일반적이다.
- 블록문은 언제나 문의 종료를 의미하는 자체 종결성을 갖기 때문에 블록문의 끝에는 세미콜론을 붙이지 않는다.

```
// 블록문
{ 
  var foo = 10;
}

// 제어문
var x = 1;
if(x<10){
 x++;
}

// 함수 선엄누
function sum(a,b) {
  return a+b;
}
```

---

### 📖 조건문

주어진 조건식의 평가 결과에 따라 코드블록의 실행을 결정하는 문
- if ...else 문과 switch문으로 두 가지 조건문을 제공한다.

- if ...else문
  - if 문의 조건식은 불리언 값으로 평가되어야 한다.
  - 만약 if문의 조건식이 불리언 값이 아닌 값으로 평가되면 자바스크립트 엔진에 의해 암묵적으로 불리언 값으로 강제 변환되어 실행할 코드 블록을 결정한다.
  - 만약 코드 블록 내의 하나뿐이라면 중괄호를 생략할 수 있다.
 ```
 var num = 2;
 var kind;
 
 if(num > 0)       kind = '양수';
 else if (num < 0) kind = '음수';
 else              kind = '영';
 
 console.log(kind);  // 양수
     
 ```
 > if ...else문은 상항 조건 연산자로 바꿔 쓸 수 있다.
 ```
 var x =2;
 var result;
 
 if(x%2){ // 2 % 2는 0이다. 이때 0은 false로 암묵적 강제 변환된다.
  result = '홀수';
  } else {
    result = '짝수';
  }
  
  console.log(result); // 짝수
 
 ```
 이렇게도 된다.
 ```
 var x = 2;
 
 // 0은 false로 취급된다.
 var result =x % 2 ? '홀수' : '짝수';
 consoel.log(result); // 짝수
 ```
 
 
 
 
 - switch문

  > switch문의 표현식과 일치하는 case문이 없다면 실행 순서는 default문으로 이동한다. default문은 석택사항으로 사용할 수도 있고 사용하지 않을 수도 있다.
  ```
  switch(표현식){
    case 포현식 1:
      switch 문의 표현식과 표현식1이 일치하면 실행될 문;
      break;
    case 표현식2:
      switch 문의 표현식과 표현식2가 일치하면 실행될 문;
      break;
    default:
      switch 문의 표현식과 일치하는 case 문이 없을 때 실행될 문;
}
  ```
  
  ```
  var month = 11;
  var monthName;
  
  switch (month) {
    case 10: monthName = "October";
    case 11: monthName = "Nobember";
    case 12: monthName = "December";
    default: monthName = "Invalid month";
}

console.log(monthName); // Invalid month
  ```
  위 예제를 보면 'Nobermber'가 출력되지 않고 'Invalid month'가 출력된다. 
  switch 문을 탈출하지 않고 switch 문이 끝날 때까지 이후의 모든 case문과 default문을 실행했기 때문이다. 이를 폴스루(fall through)라 한다.
  이러한 결과가 나온 이유는 case문 마지막에 break 문을 사용하지 않았기 때문이다.
  break 문이 없다면 case 문의 표현식과 일치하지 않더라도 실행 흐름이 다음 case 문으로 연이어 이동한다. 
  
  올바르게 switch문을 사용하려면 아래처럼 하면된다.
  ```
  var month = 11;
  var monthName;
  
  switch (month) {
    case 10: monthName = "October";
      break;
    case 11: monthName = "Nobember";
      break;
    case 12: monthName = "December";
      break;
    default: monthName = "Invalid month";
  ```
  
  하지만 break을 일부로 생략해서 폴스루를 유용하게 사용하는 경우도 있다.
  
  ```
  var year = 2000;
  var days = 0;
  
  switch (month){
    case 1: case 3: case 5: case 7: case 8: case 10: case 12:
      days = 31;
      break;
    case4: case 6: case 9: case 11:
      days = 30;
      break;
    case 2:
      days = ((year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0)) ?29 : 28;
    default:
      console.log('Invalid month');
}
console.log(days); // 29
  ```
 ---
 
 ---
  
### 📖 반복문
  
  반복문은 조건식의 평가 결과가 참인 경우 코드 블록을 실행한다.
  그 후 조건식을 다시 평가햐여 여전히 참인 경우 코드 블록을 다시 실행한다. (이는 조건식이 거짓일 때까지 반복된다.)
  반복문에는 for 문, while 문, do ... while 문을 제공한다.
  
  
  - while 문
    - for 문은 반복 횟수가 명확할 때 주로 사용하고 while 문은 박복 횟수가 불명확할 때 주로 사용한다.
    - while 문은 조건문의 평가 결과가 거짓이 되면 코드 블록을 실행하지 않고 죵료한다.
    - 만약 조건식의 평가 겨로가가 불리언 값이 아니면 불리언 값으로 강제 변환하여 논리적 참, 거짓을 구별한다.
    - 조건식식의 평가 결과가 언제나 참이면 무한루프가 된다.
    - 조건식이 항상 참이 되지 않게 하거나 if문과 break를 사용해서 while문을 종료시킬 수 있다.

  - do ... while 문
    - do ...whilte 문은 코드 블록을 먼저 실행하고 조건식을 평가한다.
    - 따라서 코드 블록은 모조건 한 번 이상 실행된다.
     ```
     var count = 0;
     
     // count가 3보다 작을 때까지 코드 블록을 계속 반복 실행한다.
     do{
      console.log(count); // 0 1 2
      count++;
      } while (count < 3);
     ```
     
  - break 문
    - 레이블 문, 반복문(for, for..in, for...of, while, do...while) 또는 switch문의 코드 블록을 탈출한다.
    - 레이블 문, 반복문, switch 문의 코드 블록 외에 break 문을 사용하면 syntaxError(문법 에러)가 발생한다.
      - 레이블 문이란 식별자가 붙은 문을 말한다.
      ```
      //foo라는 레이블 식별자가 붙은 레이블 문
      foo: console.log('foo')
      ```
     
  - continue 문
    - continue 문은 반복문의 코드 블록 실행을 현 지점에서 중단하고 반복문의 증감식으로 실행 흐름을 이동시킨다.      





  
  
  
 
---

---

### 다른 분이 작성하신 TIL에 대한 소감
