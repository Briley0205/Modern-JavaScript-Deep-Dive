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

1.<br>
➡️`var x;`에서 `x`는 선언과 초기화만 이루어졌으며 암묵적으로 undefined 값을 갖고 있다. 그러므로 타입은 **undefined**이다.<br>

➡️`var y = {a:'bla'};`에서 `y.a`는 `y`에 할당된 객체 내 a가 가진 value의 타입을 구하는 것이므로, 'bla'는 string 타입. 때문에 `y.a`의 타입은 **string**이다. <br>

➡️`var z = null;`에서 z의 데이터 타입은 null이지만 typeof 연산자로 type을 구할 경우 object가 나온다.(수정되지 않은 자바스크립트의 첫번째 버그!) 때문에 `z`의 타입은 **object**이다. <br>

2.<br>
함수를 작성하기 앞서 충족해야하는 조건은 다음과 같다.<br>

- 사용한 금액에 따라 차감되어야 한다.
- 다만, 할부횟수가 함께 입력되면 그 달의 할부금만 차감되어야 한다.
- 마이너스 통장은 불가. 통장에 있는 금액보다 더 많은 금액은 출금할 수 없다.

```javascript

var 스쳐가는 통장 = 5000000;

function kakaopay (사용한 금액, 할부횟수){
    var total;
    total = 스쳐가는 통장;
    //선언 및 초기화가 된 total에 '스쳐가는 통장'을 할당해준다. 여기에서 total은 '스쳐가는 통장'의 값의 주소를 갖게 된다. (5000000)

    if(할부횟수>1){
        total = total - (사용한 금액/할부횟수)
    }//할부개월이 1보다 클 경우(있을 경우) 통장 잔액에서 할부금만 차감되게 한다.(ex.20000원에 핣부 2개월이면 10000원 차감)
    else if(useMoney > total){
        console.log("통장에 잔액이 부족합니다.");
    }
    //사용한 금액이 잔액을 초과하거나 할부횟수가 1개월 이하인 경우에는 일시불로 계
    else if(typeof 할부횟수 == "undefined" || 할부횟수 <= 1 ){
    total = myBank - 사용한 금액
    }
    //할부횟수가 undefined거나 1개월 이하인 경우 일시불로 계산한다.
  return total;
}
```

위의 조건을 충족해서 코드를 작성했으며, 출금액이 잔액을 넘을 경우 console.log로 "통장 잔액이 부족합니다." 와 현재 계좌에 있는 잔액을 보여주게 했다.
