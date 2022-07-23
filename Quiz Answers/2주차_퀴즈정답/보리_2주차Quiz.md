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

1. x : undefined , y : string , z : object 가 출력이 됩니다. 결국 다 다른타입입니다.
x는 아무것도 정의하지 않아서 undefined타입이 되고, y는 'bal'라는 문자열을 입력해서 string타입,
z는 null로 object타입으로 출력됩니다. 
솔직히 null이 object타입으로 출력해주는지 몰라서 공부하고 갑니다(__)....

2.
```js
var 스쳐가는통장 = 5000000;

function kakaopay (사용한금액, 할부횟수){
	var total = 스쳐가는통장 - (사용한금액 / 할부횟수);
	할부횟수 === undefined ? 스쳐가는통장 - 사용한금액 : total;

	if((스쳐가는통장 - 사용한금액 / 할부횟수) < 0){
		console.log('승인 거절');
		return 스쳐가는통장;
	} 
	
	return total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```
2번은 .. 시후님께 문제에 대한 많은 설명을 들었음에도 불구하고, 이런 해답밖에 나오지 못했네요 ㅠㅠ..
문제풀이같은것은 처음해 보는데, 생각보다 많이 머리를 써야하고 어렵네요.. 많이 연습하겠습니다 ㅠㅠ..

