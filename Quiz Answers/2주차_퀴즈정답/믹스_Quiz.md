### Quiz 

1. 다음 각각의 결과 중 다른 것 하나가 무엇일지 예상해보자.

```javascript
var x;
var y = { a: 'bla'};
var z = null;

console.log(typeof x);
console.log(typeof y.a);
console.log(typeof z);
```

2. 다음은 찰리의 지갑사정 입니다. 사용한 금액에 따라 차감되고, 할부횟수가 함께 입력되면 그 달의 할부금만 차감되는 카카오페이 함수를 만들어주세요. 단 해당 통장은 마이너스가 불가 합니다!

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay (사용한금액, 할부횟수){
  var total;

  //-- 작성!

  return total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```

#### 해설 및 풀이

자유롭게 풀이해주세요! 

📝 1번 풀이

```javascript
var x;
//x는 undefined
var y = { a: 'bla'};
//y는 array
var z = null;
//z는 null

console.log(typeof x); //undefined의 typeof는 undefined
console.log(typeof y.a);//y.a의 결과값은 문자열인 bla이므로 typeof는 string
console.log(typeof z);//null의 typeof는 object

// 예상 결과
// undefined
// string
// object
```
console.log(typeof y.a);이 아닌 console.log(typeof y);라면, y는 array, 즉 typeof 결과가 object겠지만, y.a의 경우 결과값이 bla이므로  console.log(typeof y.a);가 string이 될거 같습니다.<br><br>
그래서 제 생각안 console.log가 순서대로<br>
undefined<br>
string<br>
object<br>
가 되고 세개의 결과가 모두 다를것으로 예상되어집니다.


📝 2번 풀이

이 문제에서 고려해야할 사항은 세가지입니다.
1. 스쳐가는 통장에서 사용한 금액만큼 차감이 되어, 값이 재할당되어야한다. - 부수효과를 가지는 연산자를 사용
2. 할부횟수가 있는 경우, 그 달의 할부금액만큼만 차감이 되어야한다.
3. 사용한금액이 스쳐가는통장의 남은 잔액보다 크다면, 결제가 되지 않아야한다.

이 세가지의 조건으로 if문으로 함수를 작성해보았습니다.

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay (사용한금액, 할부횟수){
  var total;
  //-- 작성!
  if (사용한금액>스쳐가는통장){
    total = `결제 실패! 잔액이 부족합니다. 통장 잔고 : ${스쳐가는통장}`; // 3번 조건 - 금액을 비교하여 결제가 이루어지지 않는 조건문
  } else if (할부횟수 === undefined){
    total = 스쳐가는통장 -= (사용한금액); // 1번 조건 - 사용한 금액만큼 차감 후 재할당되는 조건문
  } else {
    total = 스쳐가는통장 -= (사용한금액/할부횟수); // 2번 조건 - 할부횟수가 있다면 그 달의 할부금액만큼만 차감되는 조건문
  }
  return total;
}


스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```