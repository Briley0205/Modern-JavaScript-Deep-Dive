### Quiz

1. 다음 각각의 결과 중 다른 것 하나가 무엇일지 예상해보자.

```javascript
var x;
var y = { a: "bla" };
var z = null;

console.log(typeof x);
console.log(typeof y.a);
console.log(typeof z);
```

2. 다음은 찰리의 지갑사정 입니다. 사용한 금액에 따라 차감되고, 할부횟수가 함께 입력되면 그 달의 할부금만 차감되는 카카오페이 함수를 만들어주세요. 단 해당 통장은 마이너스가 불가 합니다!

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay(사용한금액, 할부횟수) {
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

1번
`var x` // undefined
선언만 이루어지고 재할당이 이루어지지않았으므로.

`var y` // string
a에 'bla'라는 문자열이 재할당되었으므로.

`var z` // object
null의 타입이 object인 것은 자바스크립트의 유구한(?) 버그이므로.

---

2번
우선 제출된 부분은 수정하지 않고 답안을 작성해보았습니다.

```javascript
var 스쳐가는통장 = 5000000;

// 지불금액을 계산하고 그 금액을 통장에서 차감하는 함수
function kakaopay(사용한금액, 할부횟수) {
  var total;
  // 할부횟수가 지정되지 않았을 시, 일시불로 지정
  if (!할부횟수) { 할부횟수 = 1 }

  total = 사용한 금액 / 할부횟수;

  // 통장이 마이너스가 될 시 에러처리
  if(total > 스쳐지나가는통장) return new Error("잔고를 확인해주세요");
  return 스쳐지나가는 통장 - total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
// 여기서 에러 발생
스쳐가는통장 = kakaopay(100000000000000);
```

개인적으로 조금 더 브러쉬업 해보았습니다.

먼저 두번째 매개변수인 할부횟수는 필수가 아니지만, 지정되지 않았을 경우 일시불인 경우로 판단이 가능하므로 기본값 할당을 해주었습니다. 기본값을 지정해주면 할부횟수가 undefined인지 아닌지 판단해야하는 if문을 줄여 가독성을 높일 수 있습니다. [참고](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions/Default_parameters)
다음은 조건문의 가독성을 올리기 위해 조건문을 정수에 저장해서 사용했습니다.
마지막으로 변수와 함수의 이름을 적절하게 수정했습니다. (이게 가장 어려웠네요..의견 받습니다🥲)

위 사항들을 수정한 정답은 아래와 같이 됩니다.

```jsx
// 변수 이름 변경
let baseAccount = 5000000;

// 두번째 인자에 기본값을 할당하여 불필요한 if문 삭제
function paymentFromAccount(billiingAmount, installments = 1) {
  const montlyPayment = billiingAmount / installments;
  // 조건문을 정수에 할당
  const isPayable = montlyPayment <= baseAccount;
  if (!isPayable) return new Error("잔고를 확인해주세요");

  const balance = baseAccount - montlyPayment;
  return balance;
}

baseAccount = paymentFromAccount(12000);
baseAccount = paymentFromAccount(44000);
baseAccount = paymentFromAccount(200000, 2);
baseAccount = paymentFromAccount(500000, 2);
baseAccount = paymentFromAccount(100000000000000);
```
