## 📕 『모던 자바스크립트 Deep Dive』 오늘 읽은 내용 ✒

**TIL(Today I learn) 기록일** : 2022.08.31

### 29장 Date 📑

> 날짜와 시간(연, 월, 일, 시, 분, 초, 밀리초(천분의 1초))을 위한 메서드를 제공하는 빌트인 객체이면서 생성자 함수다.

---
### Date 생성자 함수 
Date 생성자 함수로 생성한 Date 객체는 기본적으로 현재 날짜와 시간을 나타내는 정수값을 가진다.
#### 1. new Date()
- 인수없이 new 연산자와 함께 호출 시 현재 날짜와 시간을 가지는 Date 객체를 반환한다.
- new 연산자 없이 호출 시 Date 객체를 반환하지 않고 날짜와 시간 정보를 나타내는 문자열을 반환한다.

#### 2. new Date(milliseconds)
- 숫자 타입의 밀리초를 인수로 전달하면 1970년 1월 1일 00:00:00(UTC)을 기점으로 인수로 전달된 밀리초만큼 경과한 날짜와 시간을 나타내는 Date 객체를 반환한다.

#### 3. new Date(dateString)
- 날짜와 시간을 나타내는 문자열을 인수로 전달하면 지정된 날짜와 시간을 나타내는 Date 객체를 반환한다.
- 이때 인수로 전달한 문자열은 Date.parse 메서드에 의해 해석 가능한 형식이어야 한다.

#### 4. new Date(year, month[,day,hour,minute,second,millisecond])
- 연, 월, 일, 시, 분, 초, 밀리초를 의미하는 숫자를 인수로 전달하면  지저된 날짜와 시간을 나타내는 Date 객체를 반환한다.
- 연과 월은 필수이다.

---
### Date 메서드
1. Date.now<br>
1970년 1월 1일 00:00:00(UTC)울 기점으로 현재 시간까지 경과한 밀리초를 숫자로 반환한다.

2. Date.parse<br>
1970년 1월 1일 00:00:00(UTC)울 기점으로 인수로 전달된 지정 시간(new Date(dateString)의 인수와 동일한 형식)까지의 밀리초를 숫자로 반환한다.

3. Date.UTC<br>
1970년 1월 1일 00:00:00(UTC)울 기점으로 인수로 전달된 지정 시간까지의 밀리초를 숫자로 반환한다. new Date(year, month[,day,hour,minute,second,millisecond])와 같은 형식의 인수를 사용해야 한다.

4. Date.prototype.getFullYear / setFullYear<br>
Date 객체의 연도를 나타내는 정수를 __반환__ / __설정__

5. Date.prototype.getMonth / setMonth<br>
Date 객체의 월을 나타내는 0~11의 정수를 __반환__ / __설정__ <br>1월이 0부터 시작한다.

6. Date.prototype.getDate / setDate<br>
Date 객체의 날짜를 나타내는 정수를 __반환__ / __설정__

7. Date.prototype.getDay<br>
Date 객체의 요일을 나타내는 정수를 반환<br>
일요일 - 0 부터 토요일 - 6으로 끝난다.

8. Date.prototype.getHours(/Minutes/Seconds/Milliseconds) / setHours(Minutes/Seconds/Milliseconds)<br>
Date 객체의 시간, 분, 초를 나타내는 정수를 __반환__ / __설정__<br>
시간은 0~23으로, 분과 초는 0~59, 밀리초는 0~999로 끝난다.

9. Date.prototype.getTime / setTime<br>
1970년 1월 1일 00:00:00(UTC)울 기점으로 경과된 밀리초를 __반환__ / __설정__

---