## 📕 오늘 공부한 내용, 이렇게 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 20XX.XX.XX

**오늘 읽은 범위** : 31장 RegExp

# RegExp
- 정규 표현식은 일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어다.
- 정규 표현식은 문자열을 대상으로 __패턴 매칭__ 기능을 제공한다.
  - 패턴 매칭 기능이란 특정 패턴과 일치하는 문자열을 검색하거나 추출 또는 치환할 수 있는 기능을 말한다.

### 정규 표현식의 생성
- 정규 표현식은 리터럴과 RegExp 생성자 함수를 사용할 수 있다.
  - 일반적으로는 정규 표현식 리터럴을 사용한다.
![Untitled](https://poiemaweb.com/img/regular_expression.png)
- 정규 표현식은 위 그림과 같이 패턴과 플래그로 구성된다.

### 플래그
| 플래그 | 의미 | 설명 |
| --- | --- | --- |
| i | Ignore case | 대소문자를 구별하지 않고 패턴을 검색한다. |
| g | Global | 대상 문자열 내에서 패턴과 일치하는 모든 문자열을 전역 검색한다. |
| m | Multi line | 문자열의 행이 바뀌더라도 패턴 검색을 계속한다. |
- 플래그는 옵션임으로 선택적 사용이 가능하다. 
- 순서와 상관없이 하나 이상의 플래그를 동시에 설정할 수도 있다.

## 패턴
### 문자열 검색
```
const target = 'Is this all there is?';

// 'is' 문자열과 매치하는 패턴.
// 플래그 g를 추가하면 대상 문자열 내에서 패턴과 일치하는 모든 문자열을 전역 검색한다.
const regExp = /is/ig;

target.match(regExp); // -> ["Is", "is", "is"]
```

### 임의의 문자열 검색   
- 은 임의의 문자 한 개를 의미한다.
```
const target = 'Is this all there is?';

// 임의의 3자리 문자열을 대소문자를 구별하여 전역 검색한다.
const regExp = /.../g;

target.match(regExp); // -> ["Is ", "thi", "s a", "ll ", "the", "re ", "is?"]
```

### 반복 검색
- {m,n} 은 앞선 패턴이 최소 m번, 최대 n번 반복되는 문자열을 의미한다.
```
const target = 'A AA B BB Aa Bb AAA';

// 'A'가 최소 1번, 최대 2번 반복되는 문자열을 전역 검색한다.
const regExp = /A{1,2}/g;

target.match(regExp); // -> ["A", "AA", "A", "AA", "A"]
```
- {n}은 앞선 패턴이 b번 반복되는 문자열을 의미한다. {n,n} 과 의미가 같음.
- {n,}은 앞선 패턴이 최소 n번 이상 반복되는 문자열을 의미한다.
- +는 앞선 패턴이 최소 한번 이상 반복되는 문자열을 의미한다.
- ?는 앞선 패턴이 최대 한 번(0번 포함) 이상 반복되는 문자열을 의미한다.
```
const target = 'A AA B BB Aa Bb AAA';

// 'A'가 2번 반복되는 문자열을 전역 검색한다.
const regExp = /A{2}/g;

target.match(regExp); // -> ["AA", "AA"]


// 'A'가 최소 2번 이상 반복되는 문자열을 전역 검색한다.
const regExp = /A{2,}/g;

target.match(regExp); // -> ["AA", "AAA"]


// 'A'가 최소 한 번 이상 반복되는 문자열('A, 'AA', 'AAA', ...)을 전역 검색한다.
const regExp = /A+/g;

target.match(regExp); // -> ["A", "AA", "A", "AAA"]


// 'colo' 다음 'u'가 최대 한 번(0번 포함) 이상 반복되고 'r'이 이어지는 문자열 'color', 'colour'를 전역 검색한다.
const regExp = /colou?r/g;

target.match(regExp); // -> ["color", "colour"]
```

### OR 검색
- |은 or 의미를 갖는다.
```
const target = 'A AA B BB Aa Bb';

// 'A' 또는 'B'를 전역 검색한다.
const regExp = /A|B/g;

target.match(regExp); // -> ["A", "A", "A", "B", "B", "B", "A", "B"]
```

- [] 내의 문자는 or 로 동작한다. 그 뒤에 +를 사용하면 앞선 패턴을 한 번 이상 반복한다.
```
const target = 'A AA B BB Aa Bb';

// 'A' 또는 'B'가 한 번 이상 반복되는 문자열을 전역 검색한다.
// 'A', 'AA', 'AAA', ... 또는 'B', 'BB', 'BBB', ...
const regExp = /[AB]+/g;

target.match(regExp); // -> ["A", "AA", "B", "BB", "A", "B"]
```

- 범위를 지정하려면 [] 내에 -를 사용한다.
```
const target = 'A AA BB ZZ Aa Bb';

// 'A' ~ 'Z'가 한 번 이상 반복되는 문자열을 전역 검색한다.
// 'A', 'AA', 'AAA', ... 또는 'B', 'BB', 'BBB', ... ~ 또는 'Z', 'ZZ', 'ZZZ', ...
const regExp = /[A-Z]+/g;

target.match(regExp); // -> ["A", "AA", "BB", "ZZ", "A", "B"]
```

- \d 는 숫자를 의미한다. 즉, \d는 [0-9]와 같다.
- \D는 \d 와 반대로 동작한다. 즉 \D는 숫자가 아닌 문자를 의미한다.
```
const target = 'AA BB 12,345';

// '0' ~ '9' 또는 ','가 한 번 이상 반복되는 문자열을 전역 검색한다.
let regExp = /[\d,]+/g;

target.match(regExp); // -> ["12,345"]

// '0' ~ '9'가 아닌 문자(숫자가 아닌 문자) 또는 ','가 한 번 이상 반복되는 문자열을 전역 검색한다.
regExp = /[\D,]+/g;

target.match(regExp); // -> ["AA BB ", ","]
```

- \w는 알파벳, 숫자, 언더스코어를 의미한다. 즉 \w는 [A-Za-z0-9]와 같다.
- \W는 알파벳, 숫자, 언더스코어가 아닌 문자를 의미한다.

```
const target = 'Aa Bb 12,345 _$%&';

// 알파벳, 숫자, 언더스코어, ','가 한 번 이상 반복되는 문자열을 전역 검색한다.
let regExp = /[\w,]+/g;

target.match(regExp); // -> ["Aa", "Bb", "12,345", "_"]

// 알파벳, 숫자, 언더스코어가 아닌 문자 또는 ','가 한 번 이상 반복되는 문자열을 전역 검색한다.
regExp = /[\W,]+/g;

target.match(regExp); // -> [" ", " ", ",", " $%&"]
```

### NOT 검색
- [...] sodml ^는 not 의미를 갖는다. [^0-9]는 숫자를 제외한 문자를 의미한다.
- [...] 밖의 ^은 문자열의 시작을 의미한다.

### 마지막 위치로 검색
$는 문자열의 마지막을 의미한다.
```
const target = 'https://poiemaweb.com';

// 'com'으로 끝나는지 검사한다.
const regExp = /com$/;

regExp.test(target); // -> true
```
