## π μ€λ μ½μ λ΄μ©, μ΄λ° μμΌλ‘ μ λ¦¬ν΄ λ΄μλ€. β

**TIL(Today I learn) κΈ°λ‘μΌ** : 2022.07.14

**μ€λ μ½μ λ²μ** : 7μ₯ μ°μ°μ
<br><br>

## π μ°μ°μ
- μ°μ°μ: νλ μ΄μμ ννμμ λμμΌλ‘ μ°μ , ν λΉ, λΉκ΅, λΌλ¦¬, νμ, μ§μ μ°μ° λ±μ μνν΄ νλμ κ°μ μμ±
- νΌμ°μ°μ: μ°μ°μ λμ
- νΌμ°μ°μλ κ°μΌλ‘ νκ°λ  μ μλ ννμ
<br><br>
```
νΌμ°μ°μκ° "κ°"μ΄λΌλ λͺμ¬μ μ­ν μ νλ€λ©΄ μ°μ°μλ "νΌμ°μ°μλ₯Ό μ°μ°νμ¬ μλ‘μ΄ κ°μ λ§λ λ€"λΌλ λμ¬μ μ­ν 
```
<br>

### 7.1 μ°μ  μ°μ°μ
<br>
- νΌμ°μ°μλ₯Ό λμμΌλ‘ μνμ  κ³μ°μ μνν΄ μλ‘μ΄ μ«μ κ° μμ±
- μ°μ  μ°μ°μ΄ λΆκ°λ₯ν κ²½μ°, NaNμ λ°ν

<br>

> 7.1.1 μ΄ν­ μ°μ  μ°μ°μ

- 2κ°μ νΌμ°μ°μλ₯Ό μ°μ  μ°μ°νμ¬ μ«μ κ° μμ±
- λͺ¨λ  μ΄ν­ μ°μ  μ°μ°μλ νΌμ°μ°μμ κ°μ λ³κ²½νλ λΆμ ν¨κ³Ό x
- μΈμ λ μλ‘μ΄ κ°μ μμ±

    (ex) + , - , * , / , %

<br>

> 7.1.2 λ¨ν­ μ°μ  μ°μ°μ
- 1κ°μ νΌμ°μ°μλ₯Ό μ°μ  μ°μ°νμ¬ μ«μ κ° μμ±
- μ¦κ°, κ°μ μ°μ°μλ νΌμ°μ°μμ κ°μ λ³κ²½νλ λΆμν¨κ³Ό o

    (ex) ++ , -- 

<br>

> λ¬Έμμ΄ μ°κ²° μ°μ°μ
- '+' μ°μ°μλ νΌμ°μ°μ μ€ νλ μ΄μμ΄ λ¬Έμμ΄μΈ κ²½μ° λ¬Έμμ΄ μ°κ²° μ°μ°μλ‘ λμ

```
μλ¬΅μ  νμ λ³ν implicit coercion λλ νμ κ°μ  λ³ν type coercion
```

<br>

### 7.2 ν λΉ μ°μ°μ
<br>
- μ°ν­μ μλ νΌμ°μ°μμ νκ° κ²°κ³Όλ₯Ό μ’ν­μ μλ λ³μμ ν λΉ 
- μ’ν­μ λ³μμ κ°μ ν λΉνλ―λ‘ λ³μ κ°μ΄ λ³νλ λΆμ ν¨κ³Ό o
<br>
(ex) x += 5 / x-=5 / x*= 5 λ±

<br>
<br>

### 7.3 λΉκ΅ μ°μ°μ
- μ’ν­κ³Ό μ°ν­μ νΌμ°μ°μλ₯Ό λΉκ΅ν λ€μ κ·Έ κ²°κ³Όλ₯Ό λΆλ¦¬μΈ κ°μΌλ‘ λ°ν
- if λ¬Έ λλ for λ¬Έκ³Ό κ°μ μ μ΄λ¬Έμ μ‘°κ±΄μμμ μ£Όλ‘ μ¬μ©

<br>

> 7.3.1 λλ±/μΌμΉ λΉκ΅ μ°μ°μ
- μ’ν­κ³Ό μ°ν­μ νΌμ°μ°μκ° κ°μ κ°μΌλ‘ νκ°λλμ§ λΉκ΅ν΄ λΆλ¦¬μΈ κ° λ°ν
- λλ± λΉκ΅ μ°μ°μ: λμ¨ν λΉκ΅ / μΌμΉ λΉκ΅ μ°μ°μ: μκ²©ν λΉκ΅
- λλ± λΉκ΅λ μ’ν­κ³Ό μ°ν­μ νΌμ°μ°μλ₯Ό λΉκ΅ν  λ λ¨Όμ  μλ¬΅μ  νμ λ³νμ ν΅ν΄ νμμ μΌμΉμν¨ ν κ°μ κ°μΈμ§ λΉκ΅


```
λλ± λΉκ΅ x == y
μΌμΉ λΉκ΅ x === y
λΆλλ± λΉκ΅ x != y
λΆμΌμΉ λΉκ΅ x !== y
```

- μΌμΉ λΉκ΅μμ NaNμ μμ κ³Ό μΌμΉνμ§ μλ μ μΌν κ° -> Number.isNaN(NaN)

<br>
> 7.3.2 λμ κ΄κ³ λΉκ΅ μ°μ°μ

<br>
### 7.4 μΌν­ μ‘°κ±΄ μ°μ°μ
- μΌν­ μ‘°κ±΄ μ°μ°μ ννμμ κ°μ²λΌ μ¬μ© o / if ...else λ¬Έμ κ°μ²λΌ μ¬μ© x

<br>
### 7.5 λΌλ¦¬ μ°μ°μ
- || λλ && λλ !
- λΌλ¦¬ λΆμ  μ°μ°μ(!)λ μΈμ λ λΆλ¦¬μΈ κ°μ λ°ν

<br>

### 7.6 μΌν μ°μ°μ
- μΌμͺ½ νΌμ°μ°μλΆν° μ°¨λ‘λλ‘ νΌμ°μ°μλ₯Ό νκ°νκ³  λ§μ§λ§ νΌμ°μ°μμ νκ°κ° λλλ©΄ λ§μ§λ§ νΌμ°μ°μμ νκ° κ²°κ³Όλ₯Ό λ°ν

<br>

### 7.7 κ·Έλ£Ή μ°μ°μ
- μκ΄νΈ() λ‘ νΌμ°μ°μλ₯Ό κ°μΈλ κ·Έλ£Ή μ°μ°μλ μμ μ νΌμ°μ°μμ ννμμ κ°μ₯ λ¨Όμ  νκ°
- μ°μ μμ μ‘°μ  κ°λ₯

<br>

### 7.8 typeof μ°μ°μ
- typeof μ°μ°μλ‘ null κ°μ μ°μ°ν΄λ³΄λ©΄ "null"μ΄ μλ "object"λ₯Ό λ°ν (JSμ λ²κ·Έ) 

<br>

### 7.9 μ§μ μ°μ°μ
- μ’ν­μ νΌμ°μ°μλ₯Ό λ°μΌλ‘, μ°ν­μ νΌμ°μ°μλ₯Ό μ§μλ‘ κ±°λ­ μ κ³±νμ¬ μ«μ κ° λ°ν

    (ex) 2 ** 2 // 4

- ν λΉ μ°μ°μμ ν¨κ» μ¬μ©

    (ex) var num = 5; num **= 2 // 25 

<br>
<hr>
<br>
