## ๐ ์ค๋ ๊ณต๋ถํ ๋ด์ฉ, ์ด๋ ๊ฒ ์ ๋ฆฌํด ๋ด์๋ค. โ

**TIL(Today I learn) ๊ธฐ๋ก์ผ** : 2022.07.16

**์ค๋ ์ฝ์ ๋ฒ์** : 8์ฅ ์ ์ด๋ฌธ

### ์ ์ด๋ฌธ, control statement! ๐

- ์ผ๋ฐ์ ์ผ๋ก ์ฝ๋๋ ์์์ ์๋ ๋ฐฉํฅ์ผ๋ก ์์ฐจ์ ์ผ๋ก ์คํ๋์ง๋ง, ์ ์ด๋ฌธ์ ์ฌ์ฉํ๋ฉด ์ฝ๋์ ์คํ ํ๋ฆ์ ์ธ์์ ์ผ๋ก ์ ์ดํ  ์ ์๋ค.

---

### ๋จ์ด์ฅ ๐

๋ธ๋ก๋ฌธ(block statement/compound statement)

```
0๊ฐ ์ด์์ ๋ฌธ์ ์ค๊ดํธ{}๋ก ๋ฌถ์ ๊ฒ์ผ๋ก, ์ฝ๋ ๋ธ๋ก ๋๋ ๋ธ๋ก์ด๋ผ๊ณ  ๋ถ๋ฅด๊ธฐ๋ ํ๋ค. ์๋ฐ์คํฌ๋ฆฝํธ๋ ๋ธ๋ก๋ฌธ์ ํ๋์ ์คํ๋จ์๋ก ์ทจ๊ธํ๋ค. ๋ธ๋ก๋ฌธ์ ๋จ๋์ผ๋ก ์ฌ์ฉํ  ์๋ ์์ผ๋, ์ผ๋ฐ์ ์ผ๋ก ์ ์ด๋ฌธ์ด๋ ํจ์๋ฅผ ์ ์ํ  ๋ ์ฌ์ฉํ๋ ๊ฒ์ด ์ผ๋ฐ์ ์ด๋ค.
```

์กฐ๊ฑด๋ฌธ(conditional statement)

```
์๋ฐ์คํฌ๋ฆฝํธ๋ if...else ๋ฌธ๊ณผ switch ๋ฌธ์ผ๋ก ๋๊ฐ์ง ์กฐ๊ฑด๋ฌธ์ ์ ๊ณตํ๋ค. ์กฐ๊ฑด๋ฌธ์ ์ฃผ์ด์ง ์กฐ๊ฑด์(conditional expression)์ ํ๊ฐ ๊ฒฐ๊ณผ์ ๋ฐ๋ผ ์ฝ๋๋ธ๋ก์ ์คํ์ ๊ฒฐ์ ํ๋ค. ์กฐ๊ฑด์์ ๋ถ๋ฆฌ์ธ ๊ฐ์ผ๋ก ํ๊ฐ๋  ์ ์๋ ํํ์์ด๋ค.

if...else ๋ฌธ์ ์กฐ๊ฑด์์ ๋ถ๋ฆฌ์ธ ๊ฐ์ผ๋ก ํ๊ฐ๋๊ณ , ๋ผ๋ฆฌ์  ์ฐธ/๊ฑฐ์ง์ ์คํํ  ์ฝ๋ ๋ธ๋ก์ ๊ฒฐ์ ํ๋ค.
switch ๋ฌธ์ ํํ์์ ๋ถ๋ฆฌ์ธ ๊ฐ๋ณด๋ค๋ ๋ฌธ์์ด์ด๋ ์ซ์ ๊ฐ์ธ ๊ฒฝ์ฐ๊ฐ ๋ง๊ณ , ๋ผ๋ฆฌ์  ์ฐธ/๊ฑฐ์ง๋ณด๋ค๋ ๋ค์ํ ์ํฉ(case)์ ๋ฐ๋ผ ์คํํ  ์ฝ๋ ๋ธ๋ก์ ๊ฒฐ์ ํ  ๋ ์ฌ์ฉํ๋ค.
* switch ๋ฌธ์ ์คํํ  ๋, switch ๋ฌธ์์ ํ์ถํ  ์ ์๋๋ก break๋ฅผ ๊ฑธ์ด์ฃผ์ง ์์ผ๋ฉด switch ๋ฌธ์ด ๋๋  ๋๊น์ง ๋ชจ๋  case๋ฌธ๊ณผ default ๋ฌธ์ ์คํํ๋ค. ์ด๊ฒ์ ํด์ค๋ฃจfall through๋ผ๊ณ  ๋ถ๋ฅธ๋ค.

๋ง์ฝ if...else ๋ฌธ์ผ๋ก ํด๊ฒฐํ  ์ ์๋ค๋ฉด switch๋ฌธ๋ณด๋ค if...else ๋ฌธ์ ์ฌ์ฉํ๋ ํธ์ด ์ข๋ค. ํ์ง๋ง ์กฐ๊ฑด์ด ๋๋ฌด ๋ง์ if...else๋ฌธ๋ณด๋ค switch๋ฌธ์ ์ฌ์ฉํ๋ ์ชฝ์ด ๊ฐ๋์ฑ์ด ๋ ๋๋ค๋ฉด switch๋ฌธ์ ์ฌ์ฉํ๋ ๊ฒ์ด ์ข๋ค.
```

๋ฐ๋ณต๋ฌธ(loop statement)

```
๋ฐ๋ณต๋ฌธ์ ์กฐ๊ฑด์์ ํ๊ฐ ๊ฒฐ๊ณผ๊ฐ ์ฐธ์ธ ๊ฒฝ์ฐ ์ฝ๋ ๋ธ๋ก์ ์คํํ๋ค. ๊ทธ ํ ์กฐ๊ฑด์์ ๋ค์ ํ๊ฐํด ์ฌ์ ํ ์ฐธ์ธ ๊ฒฝ์ฐ ๊ฑฐ์ง์ด ๋  ๋๊น์ง ๋ฐ๋ณตํด์ ์ฝ๋๋ธ๋ก์ ๋ค์ ์คํํ๋ค.
์๋ฐ์คํฌ๋ฆฝํธ๋ for๋ฌธ, while๋ฌธ, do...while๋ฌธ์ ์ ๊ณตํ๋ค.

for๋ฌธ์ ์กฐ๊ฑด์์ด ๊ฑฐ์ง์ผ๋ก ํ๊ฐ๋  ๋ ๊น์ง ์ฝ๋๋ธ๋ก์ ๋ฐ๋ณต ์คํํ๋ค. while๋ฌธ์ ์กฐ๊ฑด์์ ํ๊ฐ ๊ฒฐ๊ณผ๊ฐ ์ฐธ์ด๋ฉด ์ฝ๋ ๋ธ๋ก์ ๊ณ์ํด์ ๋ฐ๋ณต ์คํํ๋ค. for ๋ฌธ์ ๋ฐ๋ณต ํ์๊ฐ ๋ชํํ๊ฒ ์ ํด์ ธ ์์ ๋ ์ฃผ๋ก ์ฌ์ฉํ๊ณ  while๋ฌธ์ ๋ฐ๋ณต ํ์๊ฐ ๋ถ๋ชํํ  ๋ ์ฃผ๋ก ์ฌ์ฉํ๋ค.
do...while๋ฌธ์ ์ฝ๋๋ธ๋ก์ ๋จผ์  ์คํํ๊ณ  ์กฐ๊ฑด์์ ํ๊ฐํ๊ธฐ ๋๋ฌธ์ ์ฝ๋ ๋ธ๋ก์ ๋ฌด์กฐ๊ฑด ํ๋ฒ ์ด์ ์คํ๋๋ค.
```

break ๋ฌธ๊ณผ continue ๋ฌธ

```
break๋ ์ฝ๋ ๋ธ๋ก์ ํ์ถํ๋ค. break๋ฅผ ์ฌ์ฉํ  ์ ์๋ ์ฝ๋๋ธ๋ก์ ๋ ์ด๋ธ๋ฌธ, ๋ฐ๋ณต๋ฌธ, switch๋ฌธ์ด๊ณ  ๊ทธ ์ธ์๋ ์ฌ์ฉํ  ๊ฒฝ์ฐ SyntaxError๊ฐ ๋ฐ์ํ๋ค.

continue๋ ๋ฐ๋ณต๋ฌธ์ ์ฝ๋ ๋ธ๋ก ์คํ์ ํ ์ง์ ์์ ์ค๋จํ๊ณ  ๋ฐ๋ณต๋ฌธ์ ์ฆ๊ฐ์์ผ๋ก ์คํ ํ๋ฆ์ ์ด๋์ํจ๋ค.
```

### ๋ ์ค๋ฅด๋ ์๊ฐ์ด ์์๋์? ๋์ ์ฌ์์ ๊ธฐ๋กํด ๋ด์๋ค ๐ญ

```

```

---

### ๋ค๋ฅธ ๋ถ์ด ์์ฑํ์  TIL์ ๋ํ ์๊ฐ

```

```
