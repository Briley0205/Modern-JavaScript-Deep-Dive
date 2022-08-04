## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.08.05

**오늘 읽은 범위** : 18장 함수와 일급 객체

### 일급 객체로서의 함수 📑

- 객체는 값이므로 함수는 객체(값)이 들어갈 수 있는 곳 어디든 쓸 수 있다.
- 함수는 객체의 특징과 더불어 고유의 프로퍼티를 가진다.

---

### 함수의 고유 프로퍼티에 관하여 🪔

🎨 `> arguments` : 함수 호출 시 전달된 인수를 담은 유사 배열 객체</br>

배열 객체는 아니기 때문에 간접 호출해야 한다.

> 함수 내부에서 arguments객체를 지역변수처럼 참조할 수 있다.
```js
// 타입스크립트처럼, 함수에 넣은 인자의 개수 또한 확인할 수 있다.
function dictionary(word, dictionary, meaning) {
    console.log(arguments.length);
    if (arguments.length !== 3) {
        console.log(`dictionary needs 3 arguments. But you put ${arguments.length} arguments here.`);
    }
}
dictionary('pen'); // dictionary needs 3 arguments. But you put 1 arguments here.
dictionary('pen', {}, 'we use it to write something');
```


📞 `> caller` : 함수 자신을 호출한 함수</br>

🧶 `> length` : 함수를 정의할 시, 선언한 매개변수의 갯수이다.</br>

📧 `> name` : 함수 이름 또는 함수 객체를 가리키는 식별자</br>

💾 `> prototype` : 생성자 함수가 생성할 인스턴스의 프로토타입 객체</br>

### 단어장 (모르는 용어가 있었다면, 간단히 정리해 봅시다) 🔖
```
유사 배열 객체
 : length 프로퍼티를 가졌으며, for문으로 순회할 수 있는 객체
```
