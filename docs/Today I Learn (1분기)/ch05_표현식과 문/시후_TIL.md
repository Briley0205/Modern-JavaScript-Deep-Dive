## 📕 오늘 읽은 내용, 이런 식으로 정리해 봅시다. ✒

**TIL(Today I learn) 기록일** : 2022.07.08

**오늘 읽은 범위** : 5장 표현식과 문

### 컴퓨터 공학 용어 정리 특집 📑

---

### 📖 값과 리터럴

값은 기본적으로 리터럴을 통해 생성된다.

> 리터럴과 연산자를 통해 만들어질 때

1 + 3 // 4 </br>
(리터럴) 연산자 (리터럴) = 값</br>

또한 모든 값은 `데이터 타입`을 가지고 `2진수`로 번역되어 메모리에 저장되기 때문에, 문자열("hi") 또는 불리언(true) 리터럴이라 할지라도 이는 모두 값을 생성하는 표기법이라 볼 수 있다.

---

### 📖 문과 표현식

> 문 ⊃ 표현식 

모든 표현식은 문이다. 하지만 표현식이 아닌 문도 있다.</br>
이를 구별하기 위해서는, 값으로 평가될 수 있는 문인지 살펴야 한다.

```html
<div style="width: 200px; height: 200px; background: tomato; border-radius: 50%; display: flex; flex-direction: column;align-items: center;">
    <p style="height: 40px;">문</p>
    <div style="width: 150px; height: 150px; background: teal; border-radius: 50%; text-align: center;">표현식
        <p style="text-align: center;">= 값으로 평가될 </p>
        <p>수 있는 문</p>
    </div>
</div> 
```

```
 |---------------|----------------|
 |               문               |
 |   |------------------------|   |
 |   |         표현식         |   |
 |   | = 값으로 평가될 수 있는 |   |
 |   |           문           |   |
 |---------------|----------------|
```

---

### 단어장 🔖
```
값 : 표현식이 평가되어 생성된 결과

<>
리터럴 : 사람의 언어 및 기호로 값을 생성하는 표기법

표현식 : 값을 반환하는 식 또는 코드 (값으로 평가되는 문)
> 리터럴은 값으로 평가되기 때문에 리터럴 또한 표현식이다.

문 : 프로그램을 구성하는 기본 단위이자 최소 실행 단위
(또는 명령문 --> 컴퓨터에 명령을 내리는 단위를 말함)
</>
```

---

### 다른 분이 작성하신 TIL에 대한 소감

