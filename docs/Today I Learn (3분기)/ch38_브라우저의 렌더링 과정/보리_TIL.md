## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.07

**오늘 읽은 범위** : 38장 브라우저의 렌더링 과정

### 랜더링 ?
+ HTML,CSS,JS로 작성된 문서를 파싱하여 브라우저에 시각적으로 출력하는 것을 말함!

### 브라우저 렌더링 과정
1. 브라우저는 HTML,CSS,JS,이미지등 렌더링에 필요한 리소스를 요청하고 서버로부터 응답을 받음
2. 렌더링 엔진은 서버로부터 응답된 HTML,CSS를 파싱하여 DOM,CSSOM을 생성하고 이들을 결합하여 렌더 트리를 생성
3. JS엔진은 서버로부터 응답된 JS를 파싱하여 AST를 생성하고 바이트코드로 변환하여 실행. 이때 JS는 DOM API를 통해 DOM이나 CSSOM을 변경할 수 있음. 변경된 DOM, CSSOM은 다시 렌더 트리로 결합.
4. 렌더 트리를 기반으로 HTML요소의 레이아웃을 계산하고 브라우저 화면에 HTML요소를 페인팅함

### 요청과 응답
+ 서버에 요청 request하고 , 서버로부터 응답 response을 받아 브라우저에 시각적으로 렌더링 하는 것.
+ 즉,렌더링에 필요한 리소스는 모두 서버에 존재하므로 필요한 리소스를 서버에 요청하고 서버가 응답한 리소스를 파싱하여 렌더링 하는 것


### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
+ 파싱 ? 토큰들의 집합을 구문 분석하여 AST를 생성! AST: Abstract Syntax Tree 추상적 구문 트리
+ AST는 토큰에 문법적 의미와 구조를 반영한 트리 구조의 자료 구조임
