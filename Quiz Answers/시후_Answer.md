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

1. 다음의 변수들은 각각 다른 타입을 가리킨다.

```javascript
var x;
var y = { a: 'bla'};
var z = null;

console.log(typeof x); // undefined
console.log(typeof y.a); // string
console.log(typeof z); // object
```

결과 중 다른 하나가 발생하려면 이렇게 작성하면 된다.
```js
console.log(typeof x); // undefined
console.log(typeof y); // object
console.log(typeof z); // object
```
▶ `typeof y.a`이 object가 아닌 string인 이유는?</br>
 : 변수 y는 객체를 가리키고 있다.</br> 하지만, y.a는 객체가 가진 프로퍼티 a의 값, 'bla'를 가리키고 있기 때문에, string으로 출력된다.

▶ `typeof null`이 null이 아닌 object를 가리키는 이유는?</br>
 : 이는 자바스크립트를 구현할 때 발생한 원초적인 버그이다. </br>
 +혹자는 null이 빈 객체를 가리키고, 참조 자료형이기 때문이라 한다.</br>
 
2. 카카오페이 통장 함수 정의하기

> **이 문제에서 해결해야 하는 과제** : 통장 잔고 관리

**작은 단위로 분해하여 확인해야 하는 점** : </br>
✅ 결제 할 수 있는 금액인가 ?</br>
```js
 if (사용한금액 > total) {
    console.log(`승인거절 남은 금액: ${total}`);
    return total
  } 
```
✅ 할부를 선택했는가 ? </br>

```js
  let 일시불결제 = total - 사용한금액; 
  // 할부횟수 = undefined일 시
  let 할부결제 = total - 사용한금액 / 할부횟수; 
  // typeof 할부횟수 === "number"일 시
  total = 할부횟수 ? 할부결제 : 일시불결제
```

따라서 전체 코드 소스는 이렇게 된다.

```js
var 스쳐가는통장 = 5000000;

function kakaopay(사용한금액, 할부횟수) {
  var total = 스쳐가는통장;
  let 일시불결제 = total - 사용한금액;
  let 할부결제 = total - 사용한금액 / 할부횟수;
  
  if (사용한금액 > total) {
    console.log(`승인거절 남은 금액: ${total}`);
    return total;
  } else {
    total = 할부횟수 ? 할부결제 : 일시불결제;
  }
  console.log(total);
  return total;
}

스쳐가는통장 = kakaopay(12000); // 4988000
스쳐가는통장 = kakaopay(44000); // 4944000
스쳐가는통장 = kakaopay(200000, 2); // 4844000
스쳐가는통장 = kakaopay(500000, 2); // 4594000
스쳐가는통장 = kakaopay(100000000000000); // 승인거절 남은 금액: 4594000
```

