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

---

#### 해설 및 풀이

1번 
```
var x; 가 다르게 나올 것 같다. 
x는 할당이 없기때문에  undefined라고 나오고 
y는 string
z는 뭐가나올까 ? null??  console.log 해보니 object가 나온다.   구글링해보니 자바스크립트 초기 설계오류 이고 계속 고치지 않는다고한다. 고치면 위험하다고 한다 https://archive.ph/sPyGA#selection-107.1-107.169
```
2번
```
var 스쳐가는통장 = 5000000;
function kakaopay (사용한금액, 할부횟수){
  var total;
  if(할부횟수){
      if(스쳐가는통장 - 사용한금액/할부횟수 < 0) return 스쳐가는통장
      total = 스쳐가는통장 - 사용한금액/할부횟수
  }else{
      if(스쳐가는통장 - 사용한금액 < 0) return 스쳐가는통장
    total = 스쳐가는통장 - 사용한금액
  }
  return total;
}

스쳐가는통장 = kakaopay(12000);
스쳐가는통장 = kakaopay(44000);
스쳐가는통장 = kakaopay(200000, 2);
스쳐가는통장 = kakaopay(500000, 2);
스쳐가는통장 = kakaopay(100000000000000);
```

> if문으로 만들어보았다.  0보다 작으면 함수를 바로 return시키고 그외에는 통장에서 사용한 금액이 차감되도록 하였다 단 할부가 존재하면 한달치만 차감되도록 하였다. 

---
