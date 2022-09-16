　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.16

**오늘 읽은 범위** : 44장 REST API

### REST API ?

+ REST 는 HTTP를 기반으로 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처라고 함
+ REST API 는 REST를 기반으로 서비스 API를 구현한 것을 의미!
+ REST API설계 원칙중 가장 중요한 두가지가 있는데
+ URI는 리소스를 표현해야하고, 리소스에 대한 행위는 HTTP요청 메서드로 표현함!
+ REST API의 구성요소는 자원, 행위, 표현이 있다.
+ 어제 Ajax얘기하다가 HTTP얘기가 나와서 정리했었지만, HTTP 요청 메서드는
+ GET, POST, PUT, PATCH, DELETE가 있다. ** URI에 표현하지 않음

### JSON Server 
+ JSON Server는 json파일을 사용해서 가상 REST API서버를 구축할 수 있는 툴임.
+ 설치 후 실행하면 돔. 
+ GET은 받는것이며, PUT은 특정 리소스 전체를 교체할 때 사용
+ PATCH는 리소스의 일부분만 수정할 때 사용, DELETE는 삭제할 때 사용함

---

