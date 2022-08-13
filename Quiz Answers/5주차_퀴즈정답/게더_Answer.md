제출 : 5주차 퀴즈

# MISSION

1. 에러를 고치고, Console에 다음과 같은 내용을 찍어봅시다.

다음과 같은 조건을 충족해야 합니다.

- 선언된 모든 함수는 반드시 생성자 함수 또는 메서드여야 합니다.
- 모든 인스턴스가 메서드를 소유하지 않고, 공유해야 합니다.
- `.revise` 메서드를 통해 연도를 바꾸고, 개정 여부를 알 수 있어야 합니다.
- `.getAge` 메서드로 현재 도서 나이를 계산할 수 있어야 합니다.
  객체 리터럴 사용 금지

```jsx
// 선언하는 모든 함수는 반드시 생성자 함수 또는 메서드일 것
// 프로토타입을 통한 상속을 이룰 것
// 객체 리터럴 사용 금지

const list = [
  {
    title: "Modern JS Deep Dive",
    author: "Ung Mo Lee",
    year: "2020",
  },
  {
    title: "Clean Code",
    author: "Robert C.Martin",
    year: "2009",
  },
];

function EbookInfo(book) {
  this.title = book.title;
  this.author = book.author;
  this.year = book.year;
}

EbookInfo.prototype.revise = function revise(year) {
  this.year = year;
  this.revised = true;
};

EbookInfo.prototype.getSummary = function getSummary() {
  console.log(
    this.title + " was written by " + this.author + " in " + this.year
  );
};

EbookInfo.prototype.getAge = function getAge() {
  const year = new Date().toString().split(" ")[3];
  console.log(this.title + " is " + (year - this.year) + " years old");
};

const ebook1 = new EbookInfo(list[0]);
const ebook2 = new EbookInfo(list[1]);

//\/\/\/\/\/\/\/\/\/\/\/\/\
//\/\/\ DO NOT TOUCH /\/\/\

console.log(ebook1);
console.log(ebook2);

ebook2.revise("2013");
console.log(ebook2);

console.log(ebook1.getSummary());

console.log(ebook1.getAge());
console.log(ebook2.getAge());

//\/\/\/\ DANGER /\/\/\/\\/
//\/\/\/\/\/\/\/\/\/\/\/\/\
```

### 후기

- 프로토타입을 왜 쓰는지 잘 모르겠다고 생각했는데 메서드를 제작해보는건 무척 재미있는 경험이었던 것 같습니다.
- 이슈탭에 + web IDE로 올려지니 보기에도 풀기에도 깔끔해서 좋았습니다!
