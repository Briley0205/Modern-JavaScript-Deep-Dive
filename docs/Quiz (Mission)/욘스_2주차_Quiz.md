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

1. 타입이 무엇인지 설명하기로 문제가 바뀌었어요!

```
x : undefined
값을 따로 할당하지 않았기 때문에 초기화와 동시에 undefined가 할당됩니다. undefined의 타입은 undefined!
y.a : string
'bla'는 문자열, string! 만약 y의 타입을 물었다면 object였을거예요.
z : object
null의 타입은 null이어야 할 것 같지만, 자바스크립트의 버그 때문에 null은 object가 됐습니다. 기존 코드에 영향을 줄 수 있기 때문에 아직까지 수정이 되지 않고 있다고 하네요.
```

2. 찰리님의 지갑사정이 풍요로워지길 기원합니다...

```javascript
var 스쳐가는통장 = 5000000;

function kakaopay(사용한금액, 할부횟수) {
  var total;
  var 스쳐가는통장 = 5000000;
  if (typeof 할부횟수 === "undefined") {
    할부횟수 = 1;
  }

  if (사용한금액 / 할부횟수 > 스쳐가는통장) {
    return 스쳐가는통장;
  } else {
    const 통장 = 스쳐가는통장 - 사용한금액 / 할부횟수;
    return 통장;
  }

  return total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```
