　## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.09.20

**오늘 읽은 범위** : 48장 모듈

### 모듈의 일반적 의미 ? 

+ 모듈 : 어플을 구성하는 개별적 요소로서 재사용 가능한 코드 조각을 말함! -> 모듈이 성립하려면 모듈은 자시난의 '파일 스코프'를 가질 수 있어야 함!
+ 여기서 자신만의 파일 스코프를 갖는 모듈의 모든 자산은 캡슐화되어, 다른 모듈에서 접근할 수 없다. '개별적 존재'
+ 하지만 어플에서 개별적 존재하는 모듈은 재사용이 불가해서 의미가 없음. 따라서, 모듈은 공개가 필요한 자산에 한정하여 명시적으로 선택적 공개가 가능하다. -> 'export'
+ 모듈사용자는 모듈이 export한 자산 중 일부 또는 전체를 선택해 자신의 스코프 내로 불러들여 재사용 할 수 있다. -> 'import'
+ 장점 ? 코드의 단위를 명확히 분리하고, 재사용이 좋아 개발 효율성과 유지보수성을 높일 수 있다.

### JS & Module
+ JS는 단순히 웹페이지의 보조기능을 위해 태어났기 때문에, 모듈이 성립하기 위해 필요한 파일 스코프와 import, export를 지원하지 않았다.
+ 즉, JS파일을 여러개의 파일로 분리하여 script태그로 로드해도 분리된 JS파일들은 결국 하나의 JS파일 내에 있는것 처럼 동작한다. -> JS파일은 하나의 전역을 공유
+ 따라서 전역변수가 중복되는 등의 문제가 발생하여, 이것으로는 모듈을 구현할 수 없다.
+ 그래서 제안도니 것이 CommonJS, AMD이다.
+ 브라우저 환경에서 모듈을 사용하기 위해서는 CommonJS or AMD를 구현한 모듈 로더 라이브러리를 사용해야 하는 상황이 됨.
+ NodeJS는 ECMAScript표준 사양은 아니지만 모듈 시스템을 지원함. -> 독립적인 파일 스코프를 가짐

### ES6 모듈 ESM
+ 사용법은 간단하다. script태그에 type='module' 를 추가하면 된다. 그러면 JS파일은 모듈로서 동작함.
+ 일반적인 JS파일이 아닌 ESM임을 명확히 하기 위해 파일 확장자는 mjs를 사용할 것을 권장함 !
+ 일반파일과 다르게 독자적인 모듈 스코프를 갖기 때문에, 외부 파일에서 참조할 수 없다. 모듈 스코프가 다르기 때문 !!!!
+ export키워드는 선언문 앞에 사용한다. -> 변수, 함수, 클래스 등 모든 식별자 가능!
+ import키워드는 다른 모듈에서 export한 식별자를 자신의 모듈 스코프 내부로 로드하려면 import를 사용한다.
+ export한 식별자 이름으로 import해야 한다.
+ 모듈에서 하나의 값만 export한다면, default키워드를 사용할 수 있다. 이 경우에는 기본적으로 이름 없이 하나의 값을 export한다.
+ default키워드를 사용하는 경우에는 var, let, const를 사용할 수없다.
---


### 떠오르는 생각이 있었나요? 나의 사색을 기록해 봅시다 💭
```
아주 좋은 기능이다.. export import란 .. ^^
이제 내일로 스터디가 끝이 난다.. 함께 참여하신 모든분들 덕분에 포기하지 않고 정독할 수 있게 되어 기쁘고, 완벽하게는 아니지만서도, 많이 JS에 가까워진 것 같아, 스터디가 끝나고도
몇번은 더 정독 할 계획이다 !! 마지막까지 화이팅 !
```
