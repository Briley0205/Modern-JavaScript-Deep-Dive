## π μ€λ κ³΅λΆν λ΄μ©, μ΄λ κ² μ λ¦¬ν΄ λ΄μλ€. β

**TIL(Today I learn) κΈ°λ‘μΌ** : 2022.07.16

### 9μ₯ νμ λ³νκ³Ό λ¨μΆ νκ°

##### 9.1 νμ λ³νμ΄λ?

- λͺμμ  νμ λ³ν(νμ μΊμ€ν): κ°λ°μκ° μλμ μΌλ‘ κ°μ νμμ λ³ννλ κ²
- μλ¬΅μ  νμ λ³ν(νμ κ°μ  λ³ν): κ°λ°μλ¦ μλμλ μκ΄μμ΄ ννμμ νκ°νλ λμ€μ μλ°μ€ν¬λ¦½νΈ μμ§μ μν΄ νμ λ³ν
- νμ λ³νμ΄ κΈ°μ‘΄ μμ κ°μ μ§μ  λ³κ²½νλ κ²μ μλ
- μμ μ΄ μμ± μ½λμμ μλ¬΅μ  νμ λ³νμ΄ λ°μνλμ§, λ°μνλ€λ©΄ μ΄λ€ νμμ μ΄λ€ κ°μΌλ‘ λ³νλλμ§, κ·Έλ¦¬κ³  νμ λ³νλ κ°μΌλ‘ ννμμ΄ μ΄λ»κ² νκ°λ  κ²μΈμ§ μμΈ‘ κ°λ₯ν΄μΌ νλ€. λ§μ½ νμ λ³ν κ²°κ³Όλ₯Ό μμΈ‘νμ§ λͺ»νκ±°λ μμΈ‘μ΄ κ²°κ³Όμ μΌμΉνμ§ μλλ€λ©΄ μ€λ₯λ₯Ό μμ°ν  κ°λ₯μ±μ΄ λμμ§λ€.

##### 9.2 μλ¬΅μ  νμ λ³ν

- μλ¬΅μ  νμ λ©΄νμ΄ λ°μνλ©΄ λ¬Έμμ΄, μ«μ, λΆλ¦¬μΈκ³Ό κ°μ μμ νμ μ€ νλλ‘ νμμ μλ λ³ννλ€.

##### 9.2.1 λ¬Έμμ΄ νμμΌλ‘ λ³ν

- +μ μ°μ°μμ λ¬Έμμ΄μ΄ ν¬ν¨λμ΄ μμΌλ©΄ λ¬Έμμ΄ μ°κ²° μ°μ°μλ‘ λμ
- μ¬λ² νμμ λ³νλμ§ μλλ€.

##### 9.2.2 μ«μ νμμΌλ‘ λ³ν

- -*/ λ± + λ₯Ό μ μΈν μ°μ°μλ νΌμ°μ°μλ₯Ό μ«μλ‘ νμ λ³ννλ€.
- νΌμ°μ°μ μ€ μ«μλ‘ λ³νν  μ μλ κ²½μ° νκ° κ²°κ³Όλ NaNμ΄ λλ€.

##### 9.2.3 λΆλ¦¬μΈ νμμΌλ‘ λ³ν

- false κ°μΌλ‘ νκ°λλ Falsy κ°
	- false
	- undefined
	- null
	- 0, -0
	- NaN
	- ''(λΉ λ¬Έμμ΄)
- Falsy κ° μΈμ λͺ¨λ  κ°μ λͺ¨λ trueλ‘ νκ°λλ Truthy κ°μ΄λ€. 

##### 9.3 λͺμμ  νμ λ³ν

##### 9.3.1 λ¬Έμμ΄ νμμΌλ‘ λ³ν

- String μμ±μ ν¨μλ₯Ό new μ°μ°μ μμ΄ νΈμΆνλ λ°©λ²
- Ojbect.prototype.toString λ©μλλ₯Ό μ¬μ©νλ λ°©λ²
- λ¬Έμμ΄ μ°κ²° μ°μ°μλ₯Ό μ΄μ©νλ λ°©λ²

##### 9.3.2 μ«μ νμμΌλ‘ λ³ν

- Number μμ±μ ν¨μλ₯Ό new μ°μ°μ μμ΄ νΈμΆνλ λ°©λ²
- parseInt.parseFloatν¨μλ₯Ό μ¬μ©νλ λ°©λ²(λ¬Έμμ΄λ§ μ«μ νμμΌλ‘ λ³ν κ°λ₯)
- + λ¨ν­ μ°μ  μ°μ°μλ₯Ό μ΄μ©νλ λ°©λ²
- * μ°μ  μ°μ°μλ₯Ό μ΄μ©νλ λ°©λ²

##### 9.3.3 λΆλ¦¬μΈ νμμΌλ‘ λ³ν

- Boolean μμ±μ ν¨μλ₯Ό new μ°μ°μ μμ΄ νΈμΆνλ λ°©λ²
- !λΆμ  λΌλ¦¬ μ°μ°μλ₯Ό λ λ² μ¬μ©νλ λ°©λ²

##### 9.4 λ¨μΆ νκ°

##### 9.4.1 λΌλ¦¬ μ°μ°μλ₯Ό μ¬μ©ν λ¨μΆ νκ°

- λΌλ¦¬κ³± μ°μ°μλ λΌλ¦¬ μ°μ°μ κ²°κ³Όλ₯Ό κ²°μ μλ λ λ²μ§Έ νΌμ°μ°μ, μ¦ λ¬Έμμ΄ 'Dog'λ₯Ό κ·Έλλ‘ λ°ννλ€.
- λΌλ¦¬ν© μ°μ°μλ λΌλ¦¬ μ°μ°μ κ²°κ³Όλ₯Ό κ²°μ ν μ²« λ²μ¨° νΌμ°μ°μ, μ¦ λ¬Έμμ΄ 'Cat'μ κ·Έλλ‘ λ°ννλ€.
- λΌλ¦¬ μ°μ°μ κ²°κ³Όλ₯Ό κ²°μ νλ νΌμ°μ°μλ₯Ό νμ λ³ννμ§ μκ³  κ·Έλλ‘ λ°ννλ€. μ΄λ₯Ό λ¨μΆ νκ°λΌ νλ€. λ¨μΆ νκ°λ ννμμ νκ°νλ λμ€μ ν΄κ° κ²°κ³Όκ° νμ λ κ²½μ° λλ¨Έμ§ νκ° κ΄μ μ μλ΅νλ κ²μ λ§νλ€.

- κ°μ²΄λ₯Ό κ°λ¦¬ν€κΈ°λ₯Ό κΈ°λνλ λ³μκ° null λλ undefinedκ° μλμ§ νμΈνκ³  νλ‘νΌν°λ₯Ό μ°Έμ‘°ν  λ, λ¨μΆ νκ°λ₯Ό μ¬μ©νλ©΄ μλ¬λ₯Ό λ°μμν€μ§ μλλ€.
- ν¨μ ν¨κ°λ³μμ κΈ°λ³Έκ°μ μ€μ ν  λ, λ¨μΆνκ°λ₯Ό μ¬μ©ν΄ κ°λ°°λ³μμ κΈ°λ³Έκ°μ μ€μ νλ©΄ undefinedλ‘ μΈν΄ λ°μν  μ μλ μλ¬λ₯Ό λ°©μ§ν  μ μλ€.

##### 9.4.2 μ΅μλ μ²΄μ΄λ μ°μ°μ

- μ΅μλ μ²΄μ΄λ μ°μ°μ ?.μ μ’ν­μ νΌμ°μ°μκ° null λλ undefinedμΈ κ²½μ° undefinedλ₯Ό λ°ννκ³ , κ·Έλ μ§ μμΌλ©΄ μ°ν­μ νλ‘νΌν° μ°Έμ‘°λ₯Ό μ΄μ΄κ°λ€.

##### 9.4.3 null λ³ν© μ°μ°μ

- null λ³ν© μ°μ°μ ??λ μ’ν­μ νΌμ°μ°μκ° null λλ undefined μΈ κ²½μ° μ°ν­μ νΌμ°μ°μλ₯Ό λ°ννκ³ , κ·Έλ μ§ μμΌλ©΄ μ’ν­μ νΌμ°μ°μλ₯Ό λ°ννλ€. null λ³ν© μ°μ°μ ??λ λ³μμ κΈ°λ³Έκ°μ μ€μ ν  λ μ μ©νλ€.

---

