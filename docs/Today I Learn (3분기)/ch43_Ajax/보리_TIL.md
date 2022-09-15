　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.15

**오늘 읽은 범위** : 43장 Ajax

### Ajax?
+ JS를 사용해서 브라우저가 서버에게 비동기 방식으로 데이터를 요청하고, 서버가 응답한 데이터를 수신하여 웹페이지를 동적으로 갱신하는 프로그래밍 방식
+ 브라우저에서 제공하는 Web API인 XMLHttpRequest 객체를 기반으로 동작.
+ XMLHttpRequest : HTTP비동기 통신을 위한 메서드와 프로퍼티를 제공
+ 예전에는 웹페이지를 렌더링할때 HTML을 서버로 부터 전송받아 처음부터 다시 렌더링하는 방식으로 동작했었음..
+ 즉 화면이 바뀔때마다 처음부터 다시 렌더링했음.. 비효율적.. 이것을 Ajax등장으로 획기적으로 바뀜!! 변경하는 부분만 렌더링하게 바뀜!

### JSON
+ 클라이언트와 서버 간의 HTTP통신을 위한 텍스트 데이터 포맷이며, JS에 종속되지 않은 언어 독립형 데이터 포맷으로 대부분의 언어에서 사용가능!
+ JSON.stringify : 객체를 JSON포맷의 문자열로 변환해줌. 클라이언트가 서버에 객체를 보낼려면 객체를 문자화 해야하는데 이를 직렬화라 함
+ JSON.parse : JSON포맷의 문자열을 객체로 변환. 위와 반대임.. 얘는 역직렬화 라고한다.

### XMLHttpRequest
+ JS를 사용하여 HTTP요청을 전송하려면 XMLHttpRequest객체를 사용함.
+ XMLHttpRequest 객체의 프로퍼티와 메서드는 제공하는게 많음. p.823참고!!
+ HTTP 요청 전송 순서 : 
1. XMLHttpRequest.prototype.open메서드로 HTTP요청을 초기화
2. 필요에 따라 XMLHttpRequest.prototype.setRequestHeader 메서드로 특정 HTTP요청의 헤더 값을 설정
3. XMLHttpRequest.prototype.send메서드로 HTTP요청을 전송

+ HTTP요청 메서드는 GET, POST, PUT, PATCH, DELETE가 있음. 얘네를 사용해서 CRUD를 구현함!
+ GET은 가져올때, POST는 새로 등록, PATCH는 부분수정, DELETE는 삭제, PUT은 치환하고자 할때 사용
+ 이 외에 OPTIONS도 있는데, 요청을 하기 전에 통신 옵션을 설명하기 위해 사용함!
---

