이음 2주차 퀴즈 정답
1.
console.log(typeof x); // undefined
console.log(typeof y.a); //string
console.log(typeof z); // object
2.
var 스쳐가는통장 = 5000000;
var 시작달 = 7;
var 이번달 = parseInt(date.getMonth());
function kakaopay(사용한금액, 할부횟수) {
 var total;
 할수횟수 = 할부횟수 || 1;
 var 월납입금액 = 사용한금액 / 할부횟수;
 if (이번달 - 시작달 < 할부횟수) {
  if (스쳐가는통장 - 월납입금액 > 0) {
   total = 스쳐가는통장 - 월납입금액;
   return total;
  } else {
   console.log(“잔액이 부족합니다.“);
  }
 }
}
스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
[해설]
1)
머릿속에서만 그려서 잘 되는 답인지 모르겠네요.
먼저 시작달은 모두 7월에 결제한 금액이라고 가정하고 이번달을 구해서 할부횟수에 맞게 통장에서 빠져나가도록 ‘이번달 - 시작달 < 할부횟수’ 조건을 달았습니다. 할부횟수를 이미 마쳤으면 통장에서 빠져나가지 않아요.
2)
월납입금액은 사용한 금액을 할부횟수로 나눈 금액입니다.
3)
할부를 내야하는 달에 해당되면 total에서 월납입금액이 빠져나가는데 잔액이 0보다 크면 total에서 할부금액이 빠져나간 값이 return 되고 0보다 작을 경우 금액은 빠져나가지 않고 ‘잔액이 부족합니다’ console이 찍힙니다.