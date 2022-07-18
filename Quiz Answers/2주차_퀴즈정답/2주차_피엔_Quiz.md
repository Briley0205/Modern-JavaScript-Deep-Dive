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
  total = 스쳐가는통장;
  if(total >= 사용한금액){
    if(할부횟수 >= 2){
      const instm = 사용한금액/할부횟수;
      total -= instm;
    }else{
      total -= 사용한금액;
    }
  }else{
    console.log("통장 잔액을 초과한 금액을 사용할 수 없습니다")
  }
  return total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```

#### 해설 및 풀이
- 퀴즈1 해설 : 3가지다 결과가 다른값이 나온다. <br>
var x 의 경우는 변수를 선언만 하고 값을 할당하지 않아 메모리 공간이 비어있는 상태이다. 그래서 첫번째 결과는 undefined 가 출력된다. <br>
var y = {a: 'bla'} 의 경우는 객체를 만들어 a : 'bla' 라는 값을 할당하였고, console.log로 객체 안에 있는 a에 할당 된 'bla'의 타입을 출력하고 결과는 string이 출력된다. <br>
var z = null 의 경우는 null은 데이터 타입 이므로, 결과로 object가 출력된다.<br><br>
- 퀴즈2 해설 : kakaopay함수 안에 total 변수에 스쳐가는 통장을 할당하여 결과 값이 유지 되도록 한다.<br> 그 뒤 if 함수를 사용해 통장 금액보다 사용한 금액이 많으면 계산실행을 하지않고 콘솔에 "통장 잔액을 초과한 금액을 사용할 수 없습니다" 문구를 띄운 후 사용한 금액을 계산하지 않고 값을 반환 한다.<br>
통장 잔액보다 사용한 금액이 적고 할부횟수가 있을경우 사용한금액/할부횟수로 사용할 금액을 나누고 instm변수를 만들어 할당한다. 그 뒤  total 값에서 instm값을 빼고 남은 값을 리턴한다.<br> 
할부가 없을 경우 스쳐가는통장에서 사용한 금액을 뺀뒤 남은 total값을 반환한다.

