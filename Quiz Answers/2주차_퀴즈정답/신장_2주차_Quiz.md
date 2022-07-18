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

1. 각 출력은 아래와 같이 출력된다. 

	- undefined
	- string
	- object

2. 소스 코드

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay (사용한금액, 할부횟수){
    var total;
    if ((typeof 할부횟수 !== 'number' && typeof 할부횟수 !== 'undefined') || 할부횟수 <= 0) return 스쳐가는통장;
    if (typeof 할부횟수 === 'undefined') 할부횟수 = 1;

    total = 스쳐가는통장 - (사용한금액 / 할부횟수);
    if (total < 0) {
        return 스쳐가는통장;
    }
    return total;
}

스쳐가는통장 = kakaopay(12000);
console.log(스쳐가는통장);
스쳐가는통장 = kakaopay(44000);
console.log(스쳐가는통장);
스쳐가는통장 = kakaopay(200000, 2);
console.log(스쳐가는통장);
스쳐가는통장 = kakaopay(500000, 2);
console.log(스쳐가는통장);
스쳐가는통장 = kakaopay(100000000000000);
console.log(스쳐가는통장);
```