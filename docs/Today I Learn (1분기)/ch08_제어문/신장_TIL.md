## ๐ ์ค๋ ๊ณต๋ถํ ๋ด์ฉ, ์ด๋ ๊ฒ ์ ๋ฆฌํด ๋ด์๋ค. โ

**TIL(Today I learn) ๊ธฐ๋ก์ผ** : 2022.07.16

### 8์ฅ ์ ์ด๋ฌธ

- ์ ์ด๋ฌธ์ ์กฐ๊ฑด์ ๋ฐ๋ผ ์ฝ๋ ๋ธ๋ก์ ์คํํ๊ฑฐ๋ ๋ณธ๋ณต ์คํํ  ๋ ์ฌ์ฉํ๋ค.

#### 8.1 ๋ธ๋ก๋ฌธ

- ๋ธ๋ก๋ฌธ์ 0๊ฐ ์ด์์ ๋ฌธ์ ์ค๊ดํธ๋ก ๋ฌถ์ ๊ฒ
- ๋ธ๋ก๋ฌธ์ ์ธ์ ๋ ๋ฌธ์ ์ข๋ฃ๋ฅผ ์๋ฏธํ๋ ์์ฒด ์ข๊ฒฐ์ฑ์ ๊ฐ๊ธฐ ๋๋ฌธ์ ๋ธ๋ก๋ฌธ์ ๋์๋ ์ธ๋ฏธ์ฝ๋ก ์ ๋ถ์ด์ง ์๋๋ค.

#### 8.2 ์กฐ๊ฑด๋ฌธ

- ์กฐ๊ฑด๋ฌธ์ ์ฃผ์ธ์ง ์กฐ๊ฑด์์ ํ๊ฐ ๊ฒฐ๊ณผ์ ๋ฐ๋ผ ์ฝ๋ ๋ธ๋ก์ ์คํ์ ๊ฒฐ์ 

#### 8.3 ๋ฐ๋ณต๋ฌธ

- ๋ฐ๋ณต๋ฌธ์ ์กฐ๊ฑด์์ ํ๊ฐ ๊ฒฐ๊ณผ๊ฐ ์ฐธ์ธ ๊ฒฝ์ฐ ์ฝ๋ ๋ธ๋ก์ ์คํํ๋ค.

### ๊ถ๊ธํ ๋ด์ฉ์ด๋, ๋ ์์๋ณด๊ณ  ์ถ์ ๋ด์ฉ์ ์ ์ด๋ด์๋ค ๐ค

- ์กฐ๊ฑด๋ฌธ์ ์กฐ๊ฑด์์ ๋ฐ๋ผ ์ด๋ป๊ฒ ํ๊ฐ๋๋์ง ํ์ธ ํ์. ์๋์ ์ฝ๋๋ฅผ ์ํํด ๋ณด์๋ค.

```jsx

num = 2;

if (num) {
    console.log("ํ๊ฐ ์ฐธ"); // ์คํ
} else {
    console.log("ํ๊ฐ ๊ฑฐ์ง");
}

num = 0;

if (num) {
    console.log("ํ๊ฐ ์ฐธ");
} else {
    console.log("ํ๊ฐ ๊ฑฐ์ง"); // ์คํ
}

if (null) {
    console.log("ํ๊ฐ ์ฐธ");
} else {
    console.log("ํ๊ฐ ๊ฑฐ์ง"); // ์คํ
}

if (undefined) {
    console.log("ํ๊ฐ ์ฐธ");
} else {
    console.log("ํ๊ฐ ๊ฑฐ์ง"); // ์คํ
}

if (`string`) {
    console.log("ํ๊ฐ ์ฐธ"); // ์คํ
} else {
    console.log("ํ๊ฐ ๊ฑฐ์ง"); 
}
```


---

