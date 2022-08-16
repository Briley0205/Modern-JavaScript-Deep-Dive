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
function EBookInfo(title, author, year) {
    this.title = title;
    this.author = author;
    this.year = year;
}

EBookInfo.prototype.printAuthorInYear = function () {
    return `${this.title} was written by ${this.author} in ${this.year}`;
}

EBookInfo.prototype.printAge = function () {
    return `${this.title} is ${this.getAge()} years old`;
}

EBookInfo.prototype.getAge = function () {
    return new Date().getFullYear() - this.year;
}

EBookInfo.prototype.revise = function (year) {
    this.year = year;
    this.revise = true;
}

const ModerJSDeepDive = new EBookInfo('Modern JS Deep Dive', 'Ung Mo Lee', '2020');
const CleanCode = new EBookInfo('Clean Code', 'Robert C. Martin', '2009');

console.log(ModerJSDeepDive);
console.log(CleanCode);
CleanCode.revise('2013');
console.log(CleanCode);

console.log(ModerJSDeepDive.printAuthorInYear());
console.log(ModerJSDeepDive.printAge());
console.log(CleanCode.printAge());

```

### 후기

- 좋은 문제 내주셔서 감사합니다!!
