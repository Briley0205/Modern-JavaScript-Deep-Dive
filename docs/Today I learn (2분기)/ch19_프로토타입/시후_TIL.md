## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.07

**오늘 읽은 범위** : 19장 프로토타입

### JS 객체 내의 상속 담당, 프로토타입 📑

- 자바스크립트는 프로토타입 기반 객체지향 언어다.
- 자식 요소(인스턴스)가 부모 요소(생성자)의 프로퍼티를 맘대로</br> 가져다 쓸 수 있도록 구현한 상속 메커니즘이다.
- 프로토타입에 추가하면 특정 인스턴스가 소유하지 않고, </br>같은 생성자에서 태어난 모든 인스턴스가 공유할 수 있는, 공유 프로퍼티가 된다.

---

### 객체지향 프로그램

> 여러 개의 독립적 단위, 객체의 집합으로 프로그램을 </br>표현하려는 패러다임이다.
**각 객체가 가지는 특징**
1. 자신의 고유한 기능을 수행한다
2. 다른 객체와의 관계성을 가진다
3. 다른 객체의 상태 데이터나 동작을 상속받아 사용한다

### 상속에 관하여 🔃

> 프로토타입 상속 후 중복 제거
```js
모든 인스턴스가 생성될 때마다 똑같은 메서드 생성시, (불필요한 복제)
||
Constructor.prototype.functionPropertyName = function () {}
으로 메서드를 공유하며, 중복 생성을 줄인다.
// 부모(생성자)에서 만들어진 자식 요소(인스턴스)에, 프로퍼티가 직접 추가되지 않는다.
// 하지만, 자식 요소가 맘대로 끌어다 쓸 수 있도록 저장한다.
```
가장 반복이 많은 api 데이터 요청 함수를 구조화하고,</br> 메서드를 상속하여 보았다.
> 생성자 함수를 이용한 방법
```js
// 글쓴이가 읽으며 직접 작성한 코드의 일부분이다.
// 타입스크립트와 함께 쓰려면 이렇게 하거나, 클래스를 대신 사용한다. 
//(클래스는 훨씬 엄격하게 문법을 준수하여, 타입스크립트가 체크하기에 가장 최적화 되어있어, 함께 쓰기에 좋다.)
function ApiData(this: any, media: string, part: string) {
  this.basePath = "https://api.movie";
  this.apiKey = "123456789";
  this.media = media;
  this.part = part;
}
ApiData.prototype.getTitleData = function() {
  return fetch(`${this.basePath}/${this.media}/${this.part}?api_key=${this.apiKey}`).then(results => results.json());
}
const nowPlayingMovie = new (ApiData as any)("movie", "now_playing");
console.log(nowPlayingMovie.getTitleData());
```
> 클래스를 이용한 방법
```js
// 클래스를 처음본 사람은 '이게 뭣이여'라며 무서워할 것이다.
// 그냥 '이런 식으로 체크하는구나...' 하고 생성자 함수와의 차이만 간단히 훑어두자
class ApiData {
  basePath: string;
  apiKey: string;
  media: string;
  part: string;
  constructor(options: {media: string, part: string}) {
    this.basePath = "https://api.movie";
    this.apiKey = "123456789";
    this.media = options.media;
    this.part = options.part;
  }
  async getTitleData() {
    const response = await fetch(`${this.basePath}/${this.media}/${this.part}?api_key=${this.apiKey}`)
    const results = await response.json();
    return results
  }
}
// 이렇게 집어넣는 방법도 있다.
ApiData.prototype.getMovieData = function() {
  return fetch(`${this.basePath}/${this.media}/${this.part}?api_key=${this.apiKey}`).then(results => results.json());
}
const nowAiringMovie = new ApiData("movie", "now_playing");
nowAiringMovie.getTitleData();
// 여기 게재한 주소와 api키는 실존하지 않는다.
// 또한, 브라우저는 타입스크립트를 이해하지 못하므로, 콘솔에 복붙해보면 에러가 발생한다.
```
### __ proto__
- `접근자 프로퍼티`로, 스스로 값을 가지지 않고, 내부 슬롯의 값을 get / set만 할 수 있다.
- 비정상적인 프로토타입 접근하는 `상호 참조`를 막기 위해</br> 접근자 프로퍼티로 체크 및 교체하도록 구현되어 있다.
- 모든 객체가 __ proto__ 접근자 프로퍼티를 사용할 수 있는</br> 것은 아니기 때문에, 코드 내에서 직접 사용하지는 않는 편이 좋다.

### 프로토타입 체인 ♻

```
자바스크립트가 식별자를 검색할 때 자식 스코프에서 전역 스코프까지
쭉 올려다보는 것처럼, 자바스크립트는 객체의 프로퍼티에 접근할 때,
객체에 해당 프로퍼티가 없다면, 프로토타입을 이용해
부모 역할을 하는 프로퍼티를 순차적으로 올려다보며 찾는다.
``` 
### 정적 프로퍼티 / 메서드 💍
> 생성자 함수 또한 하나의 객체이기 때문에 자신만의</br> 프로퍼티 / 메서드를 소유할 수 있다.
```js
function Person(name) {
  this.name = name;
}
Person.staticMethod = function() {
  console.log("It's mine. Instances can't touch it.");
}
const mySon = new Person('Jihu');
Person.staticMethod() // 스스로 호출할 수 있음
mySon.staticMethod() // 자식 요소인 인스턴스는 호출 불가
```
### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```
프로퍼티 섀도잉
 : 상속 관계에 의해 프로퍼티가 가려지는 현상
```

### 떠오르는 생각이 있었니요? 나의 사색을 기록해 봅시다 💭
```js
function Review() {
  return(
    <p>
      이제껏 당연하다는 듯 써왔던 메서드를 어떻게 쓸 수 있었는지,
      내부동작의 관점으로 '왜'에 대답할 수 있게 되었다.
      내가 따로 지정한 것도 아닌데 쓸 수 있었던 함수들
    </p>
    .length();
    .toString();
    .slice(); 
    <p>
      이들은 propotype에 연결되어 있었기 때문에,
      내가 생성한 객체 인스턴스에 연결된 체인 덕분에,
      끌어다 쓸 수 있는 것 이었다.
      또한, 이러한 메서드를 직접 작성해 prototype에 명시적으로
      추가 / 저장 하는 것으로 내가 만든 인스턴스들이 맘대로 참조할
      수 있다는 점이 가장 매력적으로 다가왔다.
      (읽자마자 바로 적용해볼 정도였으니, 그때 받았던 
      충격을 이루 말할 수 없다.)
    </p>
  );
}
function OOP() {
  return (
  <p>
    명령형 프로그래밍과 객체지향 프로그래밍이라...
    드디어 본격적으로 객체지향 프로그래밍에 대해서 들어간다!
    어서빨리 적용해서, 다음 프로젝트 코드에 나타내 봐야지!!(๑•̀ㅂ•́)و✧
    우선은 간단한 뉴스 스크래퍼부터..
  </p>
  );
}
function App() {
  return (
    <>
      <Review />
      <OOP />
    </>
  );
}
```

---

### 다른 분이 작성하신 TIL에 대한 소감