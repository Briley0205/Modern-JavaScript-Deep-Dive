## ๐ ์ค๋ ๊ณต๋ถํ ๋ด์ฉ, ์ด๋ ๊ฒ ์ ๋ฆฌํด ๋ด์๋ค. โ

**TIL(Today I learn) ๊ธฐ๋ก์ผ** : 2022.07.20

**์ค๋ ์ฝ์ ๋ฒ์** : 10์ฅ ๊ฐ์ฒด ๋ฆฌํฐ๋ด

<br>

# ๊ฐ์ฒด๋?

- ์๋ฐ์คํฌ๋ฆฝํธ: ๊ฐ์ฒด ๊ธฐ๋ฐ์ ํ๋ก๊ทธ๋๋ฐ ์ธ์ด
- ์์ ํ์์ ๊ฐ, ์ฆ ์์ ๊ฐ์ ๋ณ๊ฒฝ ๋ถ๊ฐ๋ฅํ ๊ฐ์ด์ง๋ง ๊ฐ์ฒด ํ์์ ๊ฐ, ์ฆ ๊ฐ์ฒด๋ ๋ณ๊ฒฝ ๊ฐ๋ฅํ ๊ฐ
- ์๋ฐ์คํฌ๋ฆฝํธ์ ํจ์๋ ์ผ๊ธ ๊ฐ์ฒด์ด๋ฏ๋ก ๊ฐ์ผ๋ก ์ทจ๊ธ ๊ฐ๋ฅ

```
* ํ๋กํผํฐ: ๊ฐ์ฒด ์ํ๋ฅผ ๋ํ๋ด๋ ๊ฐ (data)
* ๋ฉ์๋: ํ๋กํผํฐ(์ํ ๋ฐ์ดํฐ)๋ฅผ ์ฐธ์กฐํ๊ณ  ์กฐ์ํ  ์ ์๋ ๋์ (behavior)
```

## ๊ฐ์ฒด ๋ฆฌํฐ๋ด์ ์ํ ๊ฐ์ฒด ์์ฑ
- ํด๋์ค ๊ธฐ๋ฐ ๊ฐ์ฒด์งํฅ ์ธ์ด: C++, ์๋ฐ
    - ํด๋์ค๋ฅผ ์ฌ์ ์ ์ ์ -> ํ์ํ ์์ ์ new ์ฐ์ฐ์์ ํจ๊ป ์์ฑ์๋ฅผ ํธ์ถ -> ์ธ์คํด์ค๋ฅผ ์์ฑ
    - ์ธ์คํด์ค: ํด๋์ค์ ์ํด ์์ฑ๋์ด ๋ฉ๋ชจ๋ฆฌ์ ์ ์ฅ๋ ์ค์ฒด
    - ๊ฐ์ฒด์งํฅ ํ๋ก๊ทธ๋๋ฐ์์ ๊ฐ์ฒด๋ ํด๋์ค์ ์ธ์คํด์ค๋ฅผ ํฌํจํ ๊ฐ๋
- ํ๋กํ ํ์ ๊ธฐ๋ฐ ๊ฐ์ฒด์งํฅ ์ธ์ด: ์๋ฐ์คํฌ๋ฆฝํธ
    - ๊ฐ์ฒด ๋ฆฌํฐ๋ด์ ํตํด ๊ฐ์ฒด ์์ฑ
    - {...} ์ค๊ดํธ ๋ด์ 0๊ฐ ์ด์์ ํ๋กํผํฐ๋ฅผ ์ ์
    - ๊ฐ์ฒด ๋ฆฌํฐ๋ด ์ธ์ ๊ฐ์ฒด ์์ฑ ๋ฐฉ์์ ๋ชจ๋ ํจ์

## ํ๋กํผํฐ
- ๊ฐ์ฒด๋ ํ๋กํผํฐ์ ์งํฉ, ํ๋กํผํฐ๋ ํค์ ๊ฐ์ผ๋ก ๊ตฌ์ฑ
- ํ๋กํผํฐ ํค๊ฐ ์๋ณ์ ๋ค์ด๋ฐ ๊ท์น์ ๋ฐ๋ฅด์ง ์๋ ์ด๋ฆ์๋ ๋ฐ๋์ ๋ฐ์ดํ๋ฅผ ์ฌ์ฉ
- ํ๋กํผํฐ ํค๋ก ์ซ์ ๋ฆฌํฐ๋ด์ ์ฌ์ฉํ๋ฉด ๋ฐ์ดํ๋ ๋ถ์ง ์์ง๋ง ๋ด๋ถ์ ์ผ๋ก๋ ๋ฌธ์์ด๋ก ๋ฐํ
- ์ด๋ฏธ ์กด์ฌํ๋ ํ๋กํผํฐ ํค๋ฅผ ์ค๋ณต ์ ์ธํ๋ฉด ๋์ค์ ์ ์ธํ ํ๋กํผํฐ๊ฐ ๋จผ์  ์ ์ธํ ํ๋กํผํฐ๋ฅผ ๋ฎ์ด์

## ๋ฉ์๋
- ํ๋กํผํฐ ๊ฐ์ด ํจ์์ผ ๊ฒฝ์ฐ ์ผ๋ฐ ํจ์์ ๊ตฌ๋ถํ๊ธฐ ์ํด ๋ฉ์๋๋ผ ๋ถ๋ฆ

## ํ๋กํผํฐ ์ ๊ทผ
1) ๋ง์นจํ ํ๊ธฐ๋ฒ (.)
2) ๋๊ดํธ ํ๊ธฐ๋ฒ ([...])

- ๋๊ดํธ ํ๋กํผํฐ ์ ๊ทผ ์ฐ์ฐ์ ๋ด๋ถ์ ์ ๊ทผํ๋ ํ๋กํผํฐ ํค๋ ๋ฐ๋์ ๋ค์ดํ๋ก ๊ฐ์ผ ๋ฌธ์์ด

## ํ๋กํผํฐ ๋์  ์์ฑ
- ์กด์ฌํ์ง ์๋ ํ๋กํฌํฐ์ ๊ฐ์ ํ ๋นํ๋ฉด ํ๋กํผํฐ๊ฐ ๋์ ์ผ๋ก ์์ฑ๋์ด ์ถ๊ฐ

## ํ๋กํผํฐ ์ญ์ 
- delete ์ฐ์ฐ์

## ๊ฐ์ฒด ๋ฆฌํฐ๋ด์ ํ์ฅ ๊ธฐ๋ฅ
- ํ๋กํผํฐ ์ถ์ฝ ํํ
- ๊ณ์ฐ๋ ํ๋กํผํฐ ์ด๋ฆ
- ๋ฉ์๋ ์ถ์ฝ ํํ