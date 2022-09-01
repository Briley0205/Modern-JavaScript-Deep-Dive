　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.31

**오늘 읽은 범위** : 30장 Date

### Date?
+ 날짜와 시간을 위한 메서드를 제공하는 빌트인 객체이면서 생성자 함수임

### Date 생성자 함수
1. new Date(); 기본적으로 날짜와 시간 정보를 출력함
+ new 연산자 없이 호출하면 Date객체를 반환하지 않고 날짜와 시간 정보를 나타내는 문자열을 반환함
2. milliseconds : 밀리세컨드기준임.
+ 1초에 1,000ms , 1분이면? 60s * 1,000ms = 60,000ms
3. dateString : 날짜와 시간을 나타내는 문자열을 인수로 전달하면 지정된 날짜와 시간을 나타내는 Date객체를 반환함
4. 그외에 year, month, day, hour, minute 등등이 있다.

### Date 메서드
+ 우리가 흔히 쓰는 메서드는 getFullYear, getMonth, getDate, getDay, getHours, getMinutes, getSeconds 정도인것 같다.

```
방금 챌린지로 Date를 사용하고 와서 뭔가 더 쉽게 느껴진다.. 익숙해져서 mdn찾지 않아도 잘 할수 있게 되고싶다..!
Date는 참 유용한것 같다 !
```
