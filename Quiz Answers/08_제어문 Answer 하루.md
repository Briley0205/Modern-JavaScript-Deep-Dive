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

#### 해설 및 풀이
`undifined, string, object`   
+ x 는 변수 선언이 되고 값을 할당 받지 않았음으로 최초 선언 및 초기화 시 갖는 undifined 타입이다.
+ a 의 값은 'bla' 로 할당 되었고 type 은 string 이다.
+ z 의 값은 null 로 할당되었고 이는 object type 이다.

</br>

2. 다음은 찰리의 지갑사정 입니다. 사용한 금액에 따라 차감되고, 할부횟수가 함께 입력되면 그 달의 할부금만 차감되는 카카오페이 함수를 만들어주세요. 단 해당 통장은 마이너스가 불가 합니다!

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay (사용한금액, 할부횟수){
  스쳐가는통장 - 사용한금액

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
```javascript
var bank = 5000000;

function kakaopay(amount, count) {
  if (!count) {
    if (bank >= amount) {
      var value = bank - amount;
    } else {
      console.log("it is refused");
    }
  } else {
    var thisAmount = amount / 2;
    if (bank >= thisAmount) {
      var value = bank - thisAmount;
    } else {
     console.log("it is refused");
     } 
  }
  return value;
}

bank = kakaopay(12000);
bank = kakaopay(44000);
bank = kakaopay(200000, 2);
bank = kakaopay(500000, 2);
bank = kakaopay(100000000000000);
```

```
우선 if...else 문을 통해 할부 개월 수가 설정된 경우 or 설정되지 않은 경우 두가지 경우의 수로 나뉘었습니다.
이후 첫번 째 경우엔 통장 잔액 보다 결제 금액이 큰지 조건문을 통해 확인 하였고, 크지 않을 경우 통장 잔액에서 - 결제 금액을 해주고 return 했습니다. 
두번 째 경우에선 우선 결제 금액 / 2 를 해주었고, 그 크기가 통장 잔액보다 큰지 조건문을 통해 확인 했습니다. 
이후 크지 않음이 확인되면 통장 잔액 - 결제 금액(나누기 할부 개월 수) 를 return 했습니다.
```
