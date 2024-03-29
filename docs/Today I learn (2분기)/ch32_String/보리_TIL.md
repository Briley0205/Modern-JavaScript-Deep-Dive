　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.02

**오늘 읽은 범위** : 32장 String

### String는 원시 타입인 문자열을 다룰 때 유용한 프로퍼티와 메서드를 제공

### String 생성자 함수
+ new연산자와 함께 호출하여 String인스턴스 생성 가능
+ const strObj = new String(); //String {length:0, [[primitiveValue]]: ""}
+ [[PrimitiveValue]]라는 접근할 수 없는 프로퍼티가 보이는데, 이는 [[StringData]]내부 슬롯을 가리킴.
+ ES5에서는 StringData를 PrimitiveValue라 불렀다.

### length 프로퍼티
+ 문자열의 문자 개수를 반환해줌

### String 메서드
+ String객체에는 원본 String래퍼 객체를 직접 변경하는 메서드는 존재하지 않음.
+ String객체의 메서드는 언제나 새로운 문자열을 반환. 문자열은 변경불가능한 '원시 값' 이기 때문에 String래퍼 객체도 읽기 전용 객체로 제공됨

#### String.prototype.indexOf
+ 대상 문자열에서 인수로 전달받은 문자열을 검색하여 첫번째 인덱스를 반환해줌. 실패하면 -1을 반환

#### String.prototype.search
+ 대상 문자열에서 인수로 전달받은 정규 표현식과 매치하는 문자열을 검색하여 일치하는 문자열의 인덱스를 반환

#### includes
+ ES6에 도입되었으며, 대상 문자열에 인수로 전달받은 문자열이 포함되어 있는지 확인하여 그 결과를 Boolean값으로 반환함

#### startsWith
+ ES6에 도입되었으며, 대상 문자열이 인수로 전달받은 문자열로 시작하는지 확인하여 Boolean값으로 반환함

#### endswith
+ startsWith와 반대로 인수로 전달받은 문자열로 끝나는지 확인

#### charAt
+ 대상 문자열에서 인수로 전달받은 인덱스에 위치한 문자를 검색하여 반환함

#### substring
+ 첫 번째 인수로 전달받은 인덱스에 위치하는 문자부터 두번째 인수로 전달받은 인덱스에 위치하는 문자의 바로 이전 문자까지의 부분 문자열을 반환
+ 주의할 점은 시작인덱스 이상, 끝나는인덱스 미만임. 
```js
const str = 'Hello';
str.substring(1,4); // ell 이 출력됨. 1,2,3까지 출력
```
#### slice
+ substring와 동일하게 동작. 단 slice는 음수인 인수를 전달할 수 있다. 음수는 문자열의 가장 뒤에서부터 시작하여 문자열을 잘라냄

#### toUpperCase
+ 대상 문자열을 모두 대문자로 변경

#### toLowerCase
+ 모두 소문자로 변경

#### trim
+ 앞뒤에 공백 문자가 있을 경우 이를 제거한 문자열을 반환함

#### repeat
+ ES6에 도입되었으며, 문자열을 인수로 전달받은 정수만큼 반복해 연결한 새로운 문자열을 반환함
+ 음수면 RangeError을 발생

#### replace
+ 첫번째 인수로 전달받은 문자열 또는 정규표현식을 검색하여 두번째 인수로 전달한 문자열로 치환한 문자열을 반환함
+ 첫번째 인수를 두번째 인수로 치환함. 바꿔주는것

#### split
+ 첫 번째 인수로 전달한 문자열 또는 정규표현식을 검색하여 문자열을 구분한 후 분리된 각 문자열로 이루어진 배열을 반환함
+ 인수로 빈 문자열을 전달하면 각 문자를 모두 분리함. 인수를 생략하면 대상 문자열 전체를 단일 요소로 하는 배열을 반환함.
+ 배열을 반환하기 때문에 Array프로토타입의 reverse, join메서드와 함께 사용하면 문자열을 역순으로 뒤집을 수 있다.
