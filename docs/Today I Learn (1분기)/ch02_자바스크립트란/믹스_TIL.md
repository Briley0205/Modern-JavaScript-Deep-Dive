## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.07.05

### 2장 자바스크립트란? 📑

---

### 자바스크립트의 역사
자바스크립트란 브라우저에서 동작하는 유일한 경량 프로그래밍 언어이다.

초창기 자바스크립트는 웹페이지의 보조적인 기능을 수행하기 위해 한정적 용도로 사용되었다. 
그 당시 브라우저는 서버로부터 전달받은 HTML과 CSS를 단순히 렌더링하는 수준이었다.
즉, 우리가 웹 사이트에 접속하면 브라우저는 서버로부터 전달 받은 HTML을 렌더링하는 방식인 것이다. 그렇기 때문에 화면이 전환될 때마다 서버로부터 새로운 HTML을 받아서 다시 렌더링해야 했고 화면이 전환될 때마다 화면이 깜박이는 등의 문제가 있었다.
그러다 1999년에 자바스크립트를 통해서 서버와 브라우저가 비동기로 데이터를 주고 받을 수 있는 Ajax가 등장하게 되었다.매 번 전체 페이지에 대한 데이터를 가져올 필요 없이 필요한 부분의 데이터만 불러와서 동적으로 웹 사이트 화면을 변경할 수 있게 된 것이다.
이런 과정 속에서 여러 가지 라이브러리나 프레임워크가 만들어지기 시작했다. 2006년에는 jQuery가 등장하면서 어려운 DOM을 쉽게 컨트롤할 수 있게 되었다. 
또 CBD방법론을 기반으로 하는 SPA가 대중화되면서 Angular, React, Vue 등의 다양한 프레임워크가 활발하게 사용되고 있다.

Node.js는 브라우저의 자바스크립트 엔진에서만 동작하던 자바스크립트를 브라우저 밖의 환경에서 동자할 수 있도록 브라우저로부터 독립시킨 자바스크립트 실행환경이다.
비동기 I/O를 지원하며 단일 스레드 이벤트 루프 기반으로 동작하고 SPA에 적합하다.

---

### 자바스크립트의 특징 그리고 ECMAScript
ECMAScript는 표준 사양으로 타입, 객체 등 핵심 문법을 규정한다.
자바스크립트는 인터프리터 언어로 소스코드를 즉시 실행하고 컴파일러는 빠르게 동작하는 머신 코드를 생성하고 최적화한다.

---

### 단어장 🔖
    SPA - Single Page Application으로 하나의 페이지로 구성된 어플리케이션을 의미한다.
    MPA - Multiple Page Application으로 여러 개의 페이지로 구성된 어플리케이션을 의미한다.
    
    SSR - Server Side Rendering으로 서버쪽에서 렌더링 준비를 끝마친 상태로 클라이언트에 전달하는 방식
    CSR - Client Side Rendering으로 서버는 요청을 받으면 클라이언트에 HTML과 JS를 보내주고, 클라이언트쪽에서 그것을 받아 렌더링하는 방식. 
    동기와 비동기방식
    
    DOM - Document Object Model로 문서 객체 모델을 틋한다. XML이나 HTML 문서에 접근하기 위한 일종의 인터페이스이다. 문서 내의 모든 요소를 정의하고, 각각의 요소에 접근하는 방법을 제공한다. 
    
    스레드 - CPU의 이용의 기본단위
    단일 스레드 - 하나의 프로세스에서 하나의 스레드를 실행
    멀티 스레드 - 프로그램을 다수의 실행 단위로 나누어 실행

#### 참고 <br/>
SPA vs MPA와 SSR vs CSR 장단점 뜻정리 - https://hanamon.kr/spa-mpa-ssr-csr-장단점-뜻정리/ <br/>
DOM의 개념 - http://www.tcpschool.com/javascript/js_dom_concept <br/>
단일 스레드와 멀티 스레드 - https://beenlife.tistory.com/114
