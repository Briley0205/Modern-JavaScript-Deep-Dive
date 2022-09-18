## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.09.17

### 44장 REST API 📑

---
### REST
> HTTP 기반으로 클라이언트가 서버의 리소스에 접근하는 방식을 규정한 아키텍처

---
### REST API의 설계 원칙
< REST의 가장 중요한 기본 원칙 >
1. URI는 리소스를 표현하는데 집중
- 리소스를 식별할 수 있는 이름은 동사보단 명사
2. 행위에 대한 정의는 HTTP 요청 메서드를 통해 한다.
- 클라이언트가 서버에게 요청의 종류와 목적을 알리는 방법으로 GET,POST,PUT,PATCH,DELETE등을 사용하여 CRUD를 구현한다.
- 이 행위는 URI에 표현하지 않는다.

---
### JSON Server를 이용한 REST API
JSON Server 설치 - db.json 파일 생성 - JSON Server 실행 

---