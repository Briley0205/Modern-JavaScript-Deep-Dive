## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.27

**오늘 읽은 범위** : 27장 배열

### 배열이란 ?

+ 여러개의 값을 순차적으로 나열한 자료구조
+ 사용 빈도가 매우 높은 가장 기본적인 자료구조

### JS배열은 배열이 아니다 ?
+ 배열의 요소가 연속적으로 이어져 있지 않은 희소배열임 Sparse Array
+ 일반적인 배열의 동작을 흉내 낸 특수객체
+ 인덱스를 나타내는 문자열을 프로퍼티 키로 가지며, length프로퍼티 갖는 특수한 객체
+ 일반적인 배열과의 차이 ? 
+ 일반적인 배열은 인덱스로 요소에 빠르게 접근 가능 !!
+ JS배열은 성능적인 면에서는 느릴수 있으나, 특정 요소를 검색하거나, 요소를 삽입 또는 삭제하는 경우에는 일반적 배열보다 빠른 성능 기대 가능 !

### 배열 요소의 추가와 갱신
+ 인덱스로 정수 이외의 값을 사용하면 프로퍼티가 생성되고, 추가된 프로퍼티는 length프로퍼티 값에 영향을 주지 않는다.

### 배열 요소의 삭제
+ delete연산자로 삭제함.
+ 희소배열을 만들지 않으면서 배열의 특정 요소를 완전히 삭제하기 위해 Array.prototype.splice(index,value)를 사용

### 배열 고차 함수
+ 함수를 인수로 전달받거나 함수를 반환하는 함수를 말함.
+ JS에는 sort, filter, forEach, map, reduce, findIndex 등등이 있다.


### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
+ 평소에도 자주 쓰는 배열이라 공부하기 좀 수월했던 것 같다. 하지만 어떻게 돌아가는지는 알지만 심화학습은 못했기에, 많이 도움이 됐다.
