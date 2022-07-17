### Quiz

1. 다음 각각의 결과 중 다른 것 하나가 무엇일지 예상해보자.

```javascript
var x;
var y = { a: "bla" };
var z = null;
console.log(typeof z);
console.log(typeof x);
console.log(typeof y.a);
console.log(typeof z);
```

- 첫번째는 undefined로 선언만 하고 값을 할당하지 않아서 그렇습니다.
- 두번째는 string으로 object를 . 으로 타고 들어가서 그 값을 체크해서 그렇습니다.
- 세번째는 object로 이는 javascript의 메서드 typeof가 가지고 있는 버그 때문입니다. typeof 구현 내용에 null을 체크하는 항목이 누락되어 있어서 typeof null의 실행 결과가 object로 나오게 됩니다.

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

자유롭게 풀이해주세요!
var 스쳐가는통장 = 5000000;
function kakaopay(사용한금액, 할부횟수 = 1) {
if (사용한금액 / 할부횟수 > 스쳐가는통장) return 스쳐가는통장;
else {
const 텅장 = 스쳐가는통장 - 사용한금액 / 할부횟수;
return 텅장;
}
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
console.log(스쳐가는통장);
