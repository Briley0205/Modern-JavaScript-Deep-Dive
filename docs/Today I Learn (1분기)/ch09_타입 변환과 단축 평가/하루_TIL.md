## π μ€λ κ³΅λΆν λ΄μ©, μ΄λ κ² μ λ¦¬ν΄ λ΄μλ€. β

**TIL(Today I learn) κΈ°λ‘μΌ** : 2022.07.18

**μ€λ μ½μ λ²μ** : 9μ₯ νμ λ³νκ³Ό λ¨μΆ νκ°

### True or False π

+ λͺμμ  νμ λ³νμ΄λ μλ¬΅μ  νμ λ³νμ΄ κΈ°μ‘΄ μμ κ°μ μ§μ  λ³κ²½ν  μ μλ€. (λ³κ²½ λΆκ°λ₯ν κ°)   
  -> κΈ°μ‘΄ κ°μ μ¬ν λΉ νλ κ²μ΄ μλ μλ‘μ΄ νμμ κ°μ λ§λ€μ΄ νλ² μ¬μ©νκ³  λ²λ¦°λ€.
+ μλ°μ€ν¬λ¦½νΈ μμ§μ λΆλ¦¬μΈ νμμ΄ μλ κ°μ Truthy κ° λλ Falsy κ°μΌλ‘ κ΅¬λΆνλ€.
+ λ¨μΆ νκ°λ ννμμ νκ°νλ λμ€μ νκ° κ²°κ³Όκ° νμ λ κ²½μ° λλ¨Έμ§ νκ³Ό κ³Όμ μ μλ΅νλ κ²μ΄λ€.
```javascript
var done = true;
var message = '';

if (done) message = 'μλ£'; (if...elseλ¬Έ)
->
message = done && 'μλ£';
```
+ μ μ½λμ κ°μ΄ μ΄λ€ μ‘°κ±΄μ΄ Truthy μΌ λ λ¬΄μΈκ°λ₯Ό μννλ€λ©΄ λΌλ¦¬κ³±(&&) μ μ¬μ©ν  μ μλ€. λΌλ¦¬ν©(||) μ λ°λμΈ Falsy μΌ λ...
```javascript
var done = true;
var message = '';

message = done ? μλ£ : λ―Έμλ£;
```
+ μ μ½λμ κ°μ΄ μΌν­ μ°μ°μλ₯Ό νμ©ν  μλ μμ
+ [ES6 μ λ§€κ°λ³μ default valuse μ€μ  ](https://github.com/GEON1999/ES6/blob/main/FUNCTIONS/Arrow%20Function.md, "my github")

---

### μ±μ νκ΅¬μ  λ³΄κ΄ν¨ π

| p    | text                                           |
| ---- | ---------------------------------------------- |
| 119  | λ¨μΆ νκ°λ ννμμ νκ°νλ λμ€μ νκ° κ²°κ³Όκ° νμ λ κ²½μ° λλ¨Έμ§ νκ³Ό κ³Όμ μ μλ΅νλ κ²μ΄λ€.               |


### λ¨μ΄μ₯ (λͺ¨λ₯΄λ μ©μ΄κ° μμλ€λ©΄, κ°λ¨ν μ λ¦¬ν΄ λ΄μλ€) π
```
λͺμμ  νμ λ³ν / νμ μΊμ€ν : κ°λ°μκ° μλμ μΌλ‘ κ°μ νμμ λ³ννλ κ²
μλ¬΅μ  νμ λ³ν / νμ κ°μ  λ³ν : κ°λ°μ μλμ μκ΄ μμ΄ νκ° μ€ μλ°μ€ν¬λ¦½νΈ μμ§μ μν΄ μλ¬΅μ μΌλ‘ νμμ΄ μλ λ°ν λλ κ²
```



### λ€λ₯Έ λΆμ΄ μμ±νμ  TILμ λν μκ°
λ€λ₯Έ λΆλ€μ μ΄μ μ£Όμ°¨ ν΄μ¦μ λ΅μ λ΄€λλ°, μΌν­ μ°μ°μλ‘ κΉλνκ² μ λ¦¬ν μ½λλ€μ΄ λμ λ³΄μμ΅λλ€.   
μμ§ λ§μ΄ λΆμ‘±νμ¬ μΌν­ μ°μ°μκ° μλ if...else λ¬Έμ ν΅ν΄ μ§μ λΆνκ² μ½λ©μ νλλ° λΆν΄λ½μ ν΅ν΄ λ λ§μ΄ λ°°μΈ μ μμ κ² κ°μ΅λλ€.
