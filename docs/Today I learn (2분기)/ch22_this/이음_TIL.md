## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.15

**오늘 읽은 범위** : 22장 this


### 22.1 this 키워드
- this: 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수
- 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메소드 참조 가능
- 암묵적으로 생성

```
function Circle(radius) {
    this.radius = radius;
}
Circle.prototype.getDiameter = function() {
    return 2 * this.radius;
}
```

### 22.2 함수 호출 방식과 this 바인딩

> 일반 함수 호출
- this에는 전역 객체가 바인딩

> 메서드 호출
- 메서드 이름 앞의 마침표(.) 연산자 앞에 기술한 객체가 바인딩

> 생성자 함수 호출
- 생성자 함수가 (미래에) 생성할 인스턴스가 바인딩

> Function.prototype.apply/call/bind 메서드에 의한 간접 호출
- this로 사용할 객체와 인수 리스트를 인수로 전달 받아 함수 호출
- 메서드에 첫번재 인수로 전달한 객체