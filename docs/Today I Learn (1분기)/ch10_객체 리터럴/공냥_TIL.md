## π μ€λ κ³΅λΆν λ΄μ©, μ΄λ κ² μ λ¦¬ν΄ λ΄μλ€.

**TIL(Today I learn) κΈ°λ‘μΌ** : 2022.07.19

**μ€λ μ½μ λ²μ** : 10μ₯, κ°μ²΄ λ¦¬ν°λ΄

### β¨**λλ μΌ λ μ μλ κ°μ²΄μ ν¨μ, κ·Έλ¦¬κ³  κ°μ²΄ λ¦¬ν°λ΄**β¨

β‘οΈ**κ°μ²΄λ?** <br> -μλ°μ€ν¬λ¦½νΈλ κ°μ²΄ κΈ°λ° νλ‘κ·Έλλ° μΈμ΄λ€.<br> -κ°μ²΄λ λ³κ²½ κ°λ₯ν κ°μ΄λ€. <br> -κ°μ²΄λ 0κ° μ΄μμ νλ‘νΌν°μ λ©μλλ‘ κ΅¬μ±λ μ§ν©μ²΄λ€. <br>
μ¬κΈ°μμ νλ‘νΌν°μ λ©μλλ?

- νλ‘νΌν° : κ°μ²΄μ μνλ₯Ό λνλ΄λ κ° (data)
- λ©μλ : νλ‘νΌν°λ₯Ό μ°Έμ‘°νκ³  μ‘°μν  μ μλ λμ

βκ°μ²΄λ **μνμ λμμ νλμ λ¨μλ‘ κ΅¬μ‘°ν**ν  μ μλ€.β

<br>

β‘οΈ**κ°μ²΄ μμ±λ²** <br>
μλ°μ€ν¬λ¦½νΈλ **νλ‘ν νμ κΈ°λ° κ°μ²΄μ§ν₯ μΈμ΄**λ‘μ λ€μν κ°μ²΄ μμ± λ°©λ²μ μ§μνλ€. <br>

- κ°μ²΄ λ¦¬ν°λ΄
- object μμ±μ ν¨μ
- μμ±μ ν¨μ
- object.create λ©μλ
- ν΄λμ€(ES6)

μ΄μ€μμ μΌλ°μ μ΄λ©° κ°λ¨ν λ°©λ²μ **κ°μ²΄ λ¦¬ν°λ΄**λ‘ κ°μ²΄λ₯Ό μμ±νλ κ²μ΄λ€.

```javascript
let newObject = {};
console.log(typeof newObject);
//object

let player = {
  name: "tom", //νλ‘νΌν°
  level: 10, //νλ‘νΌν°
  defaultMotion: function () {
    console.log("do defaultMotion");
  }, //λ©μλ
};
```

β‘οΈ**νλ‘νΌν°** <br>
νλ‘νΌν°λ **ν€key**μ **κ°value**λ‘ κ΅¬μ±λλ€.<br>
νλ‘νΌν° ν€:λΉ λ¬Έμμ΄ ν¬ν¨νλ λͺ¨λ  λ¬Έμμ΄ λλ μ¬λ² κ° μ¬μ© κ°λ₯.<br>
νλ‘νΌν° κ° : μλ°μ€ν¬λ¦½νΈμμ μΈ μ μλ λͺ¨λ  κ° <br>
βνλ‘νΌν° ν€λ₯Ό μ¬μ©ν  λ μλ³μ λ€μ΄λ° κ·μΉμ λ°λ₯΄μ§ μμ μ΄λ¦μ λ°λμ λ°μ΄νλ₯Ό μ¨μ€μΌ νλ€. <br>

```javascript
let newPerson = {
  firstName: "μν¬",
  "last-name": "λ°",
};

console.log(newPerson);
//{firstName: "μν¬", last-name: 'λ°'}
```

νλ‘νΌν° ν€ `last-name`μ λ°μ΄νλ₯Ό κ°μΈμ§ μκ³  μ¬μ©ν  κ²½μ° `- μ°μ°μ`κ° μλ ννμμΌλ‘ ν΄μνλ€.

```javascript
let newPerson = {
    firstName : 'μν¬',
    last-name : 'λ°'
};

console.log(newPerson);
//μ΄ κ²½μ° syntaxErrorκ° λ°μνλ€. Unexpected token...
```

β‘οΈ**λ©μλ** <br>
μλ°μ€ν¬λ¦½νΈμ ν¨μ λν κ°μ²΄μ΄κΈ°μ κ°μΌλ‘ μ·¨κΈν  μ μμ΄μ νλ‘νΌν° κ°μΌλ‘λ μ¬μ©ν  μ μλ€. νλ‘νΌν° κ°μ΄ ν¨μμΈ κ²½μ° μΌλ° ν¨μμ κ΅¬λΆ μ§κΈ° μν΄ **λ©μλ**λΌκ³  λΆλ₯Έλ€. μ¦, κ°μ²΄μ λ¬ΆμΈ ν¨μλ₯Ό μλ―Ένλ€.

```javascript
let newPlayer = {
  level: 50,
  job: "healer",

  printLevel: function () {
    return this.level;
  }, //λ©μλ
};

newPlayer.printLevel();
```

β‘οΈ**νλ‘νΌν° μ κ·Ό** <br>
νλ‘νΌν° μ κ·Ό λ°©λ²μλ λ κ°μ§κ° μλ€.

1. λ§μΉ¨ν νκΈ°λ²
2. λκ΄νΈ νκΈ°λ²

```javascript
let newPlayer = {
  level: 50,
  job: "healer",
};

console.log(newPlayer.level); // 50
console.log(newPlayer["level"]); // 50
```

λκ΄νΈ νκΈ°λ² μ¬μ©ν  κ²½μ°, μ κ·Όνκ³ μ νλ νλ‘νΌν° ν€λ **λ°λμ λ°μ΄νλ‘ κ°μΌ λ¬Έμμ΄**μ΄μ΄μΌ νλ€.
<br>

β‘οΈ**νλ‘νΌν° κ° κ°±μ , λμ  μμ±, μ­μ ** <br>

```javascript
//νλ‘νΌν° κ° κ°±μ 
let newPlayer = {
  level: 50,
};

newPlayer.level = 30;
console.log(newPlayer); // {level: 30;}

//νλ‘νΌν° λμ  μμ±
let newPlayer = {
  level: 50,
};
newPlayer.job = "healer";
console.log(newPlayer); // {level: 50, job: 'healer'}

//νλ‘νΌν° μ­μ 
delete newPlayer.job;
console.log(newPlayer); // {level: 50}
```

---

### μ±μ νκ΅¬μ  λ³΄κ΄ν¨ π

> p. 124
> νλ‘νΌν° κ°μ΄ ν¨μμΌ κ²½μ°, μΌλ° ν¨μμ κ΅¬λΆνκΈ° μν΄ λ©μλλΌκ³  λΆλ₯Έλ€.

> p. 124
> μλ°μ€ν¬λ¦½νΈμ κ°μ²΄λ ν¨μμ λ°μ ν κ΄κ³λ₯Ό κ°μ§λ€. ν¨μμ κ°μ²΄λ λΆλ¦¬ν΄μ μκ°ν  μ μλ κ°λμ΄λ€. μ¦, κ°μ²΄λ₯Ό μ΄ν΄ν΄μΌ ν¨μλ₯Ό μ λλ‘ μ΄ν΄ν  μ μκ³  λ°λλ‘ ν¨μλ₯Ό μ΄ν΄ν΄μΌ κ°μ²΄λ₯Ό μ νν μ΄ν΄ν  μ μλ€.

<br>

---

### λ¨μ΄μ₯ (λͺ¨λ₯΄λ μ©μ΄κ° μμλ€λ©΄, κ°λ¨ν μ λ¦¬ν΄ λ΄μλ€) π

```
μΈμ€ν΄μ€ :
ν΄λμ€μ μν΄ μμ±λμ΄ λ©λͺ¨λ¦¬μ μ μ₯λ μ€μ²΄. κ°μ²΄μ§ν₯ νλ‘κ·Έλ¨μμ κ°μ²΄λ ν΄λμ€, μΈμ€ν΄μ€λ₯Ό ν¬ν¨νλ κ°λμ΄λ€. ν΄λμ€λ μΈμ€ν΄μ€λ₯Ό μμ±νκΈ° μν ννλ¦Ώμ μ­ν μ νλ€.
```

### λ μ€λ₯΄λ μκ°μ΄ μμλμ? λμ μ¬μμ κΈ°λ‘ν΄ λ΄μλ€ π­

```
λ©μλκ° μν λ°μ΄ν°μ νλ μ¦, ν¨μλΌλ κ±΄ μκ³  μμμΌλ νλ‘νΌν° λ΄μ ν¨μλ₯Ό μΌλ° ν¨μμ κ΅¬λΆ μ§κΈ° μν΄ λ©μλλΌκ³  κ΅¬λΆ μ§μ΄ λΆλ₯Έλ€λ κ±΄ μ€λμμΌ μ²μ μμλ€. κ·Έκ° TILμ μ λ¦¬νλ©° ν¨μμ λ©μλλ₯Ό μλ€κ°λ€ μΌλλ°(...) λ°μ± μ€μ΄λ€.
```

### κΆκΈν λ΄μ©μ΄λ, λ μμλ³΄κ³  μΆμ λ΄μ©μ μ μ΄λ΄μλ€ π€

```
-λ©μλ μΆμ½ ννμΌλ‘ μ μν λ©μλλ νλ‘νΌν°μ ν λΉν ν¨μμ λ€λ₯΄κ² λμνλ€. <- μ΄ μλ―Έκ° κΆκΈνλ€. μμλ₯Ό μ°Ύμλ΄μΌκ² λ€.

-μλ°μ€ν¬λ¦½νΈ νλ‘νΌν° λμ  μμ±μ νκ² λλ©΄ μ½λκ° μ’ νΌλμ€λ¬μμ§μ§ μμκΉ μκ°μ΄ λλλ°, νμμ΄λ νλ‘μ νΈμμ μ°μ΄λ κ²½μ°κ° μμκΉ? μ°μΈλ€λ©΄ μ΄λ€ μμΌλ‘ μ°μΌκΉ?
```
