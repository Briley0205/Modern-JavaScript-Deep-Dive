## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : 2022.07.15

**오늘 읽은 범위** : 8장, 제어문

### ✨**2보 전진을 위한 첫발, 제어문**✨

➡️**제어문**? <br>
조건에 따라 코드 블록을 실행(조건문)하거나, 반복 실행(반복문)할 때 사용한다.<br>

➡️**블록문**<br>
코드 블록 또는 블록. 0개 이상의 문을 중괄호로 묶은 것. 보통 제어문이나 함수를 정의할 때 사용한다.<br>

➡️**조건문**<br>
주어진 조건식의 평가 결과에 따라 블록문의 실행을 결정한다. 불리언 값으로 평가될 수 있어야 함.조건문에는 `if...else문` 과 `switch문`이 있다.<br>

`if...else문`<br>

```
if(조건식){
    조건식 참인 경우 코드 실행
}else{
    위 조건식이 거짓이면 코드 실행
}

if(조건식1){
    조건식1이 참인 경우 코드 실행
}else if(조건식2){
    조건식1이 거짓이고 조건식 가 참인 경우 코드 실행
}else{
    조건식1,조건식2가 거짓인 경우 코드 실행
}
```

`switch문`<br>
주어진 평가식을 평가한 다음 그 값과 일치한 표현식을 가진 case문으로 실행 흐름을 옮긴다. switch문의 표현식과 일치하는 case문이 없을 경우 default문으로 이동한다.(default문은 선택사항이다.)

```
var daysOfWeek = 5;
var dayName;

switch(daysOfWeek){
    case 1 : dayName = 'Monday';
    case 2 : dayName = 'Tuesday';
    case 3 : dayName = 'Wednesday';
    case 4 : dayName = 'Thursday';
    case 5 : dayName = 'Friday';
    default : dayName = 'No dayName';
}

console.log(dayName);
```

위처럼 할 경우 Friday가 아니라 No dayName이 출력된다. dayName에 Friday가 할당된 후 switch문을 탈출하지 않고 switch문이 끝날 때까지 실행했기에 No dayName이 마지막으로 재할당 된 것이다. 위 같은 현상을 **폴스루**라고 한다.

```
var daysOfWeek = 5;
var dayName;

switch(daysOfWeek){
    case 1 : dayName = 'Monday';
        break;
    case 2 : dayName = 'Tuesday';
        break;
    case 3 : dayName = 'Wednesday';
        break;
    case 4 : dayName = 'Thursday';
        break;
    case 5 : dayName = 'Friday';
        break;
    default : dayName = 'No dayName';
}

console.log(dayName); // Friday
```

폴스루를 방지하기 위한 switch문은 위처럼 작성한다. case문마다 break를 넣어줘야 한다.(일치하는 표현식을 찾은 후 switch문에서 탈출!)<br>

➡️ **반복문** <br>
조건식 평가 결과가 참인 경우 코드를 실행한다. 그후 조건식을 다시 평가해 참인 경우 코드를 재실행한다. 이는 조건식이 거짓일 때까지 반복된다. <br>

`for문`<br>

```
for(변수 선언문 또는 할당문; 조건식; 증감식){
    조건식 참인 경우 반복 실행될 문
}
```

for문 실행 순서를 하나하나 따져보자.<br>

```
for(let i = 0; i < 2; i++){
    console.log(i);
}
(1)변수 선언문 실행(let i = 0;)
(2)조건식 실행. 이때 변수값은 0이기에 조건식은 true다
(3)조건식이 true이므로 코드 실행.
(4)코드 실행 후 블록문 종료 -> 증감식 i++ 변수 값 1이 됨
(5)증감식 실행 후 다시 조건식 실행. 현재 1이므로 참이라 코드가 재실행
(6)이를 조건식이 false될 때까지 실행. false가 되면 for문이 종료됨
```

`while문` <br>
for문은 반복 횟수가 명확할 때 사용하는 반면, while문은 반복 횟수가 불명확할 때 사용한다.

```
let count = 0;
whilte(count < 3){
    console.log(count);
    count++;
}
//count가 3이 되기 전까지(3보다 작을 동안)코드 블록을 계속 실행함
```

`do-while문` <br>
코드 블록을 먼저 실행 후 조건식 평가한다. 즉 코드가 무조건 한 번 이상 실행된다.

```
let count = 0;
do{
    console.log(count);
    count++;
}while(count < 3);

//0 1 2
```

`continue문`
반복문의 코드 블록 실행을 현 지점에서 중단 후 반복문 증감식으로 실행 흐름을 이끈다.

```
let sum = 0;
    for ( let number=1; number<=4; number++)
        {if (number==4){
        continue; //아래부분을 건너뛰고 다음 반복으로 넘어감
        }
        sum = sum+number; //number가 5인 경우는 건너뜀
    }
        console.log(sum);//)+1+2+3 = 6
```

if문 내에서 실행할 코드가 길다면 continue문을 쓰는 게 가독성이 더 좋다.
<br>

---

### 책속 한구절 보관함 📖

```
➖
```

<br>

---

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖

```
레이블 문이란 식별자가 붙은 문을 말한다.
레이블 문은 for문 외부로 탈출시 유용하나 그외엔 잘 쓰이지 않는다.
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭

```
자바스크립트로 무언가를 만든 건 딱 한 번이었는데, 그때 if문을 주로 썼던 게 생각난다. 그외 switch문은 잘 쓰지 않았고... for문과 while문이 반복문이라는 건 알겠지만 실무에서는 어떻게 쓰일지 얼마나 쓰일지 궁금했다. if문 내에서 실행할 코드가 길다면 continue를 쓰는 게 더 가독성이 좋다는 건... 전혀 생각하지 못한 부분이었다 🤷‍♀️

전 코드를 보면 if조건문이 엄청 많은데(...) 개선할 수 있는 건 개선해놔야겠다.
```

### 궁금한 내용이나, 더 알아보고 싶은 내용을 적어봅시다 🤔

```
-continue를 쓰는 예제문을 좀 더 찾아봐야겠다.
-swtich문에서 폴스루를 이용하는 경우의 예제가 궁금하다.

```
