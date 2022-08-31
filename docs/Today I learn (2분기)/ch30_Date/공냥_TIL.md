# 📕 오늘 공부한 내용, 이렇게 정리해 봅시다.

**TIL(Today I learn) 기록일** : <br>
2022.08.31

**오늘 읽은 범위** : <br>
30장, Date

<br>

## ✨**30장, Date**✨

### ➡️ Date 생성자 함수

🔹new Date()<br>
Date 생성자 함수를 인수 없이 new 연산자와 함께 호출시 현재 날짜와 시간을 가지는 Date 객체를 변환한다.

🔹new Date(miliseconds)<br>
Date 생성자 함수에 숫자 타입의 밀리초를 인수로 전달시 1970년 1월 1일 00:00:00(UTC)을 기점으로 인수로 전달된 밀리초만큼 경과한 날짜와 시간을 나타내는 Date 객체를 반환한다.

🔹new Date(dateString)<br>
Date 생성자 함수에 날짜와 시간을 나타내는 문자열을 인수로 전달시 지정된 날짜와 시간을 나타내는 Date 객체를 반환한다. 이때 전달되는 문자열은 Date.parse메서드에 의해 해석 가능한 형식이어야 한다.

🔹new Date(year, month,[day, hour, minute, second, milisecond])<br>
Date 생성자 함수에 연, 월, 일, 시, 분, 초, 밀리초를 의미하는 숫자를 인수로 전달시 지정된 날짜와 시간을 나타내는 Date 객체를 반환한다. 이때 반드시 연, 월은 반드시 지정해야 한다.

<br>

### ➡️ Date 메서드

🔹Date.now<br>
1970년 1월 1일 00:00:00(UTC)을 기점으로 현재 시간까지 경과한 밀리초를 숫자로 반환.

🔹Date.parse<br>
1970년 1월 1일 00:00:00(UTC)을 기점으로 인수로 전달된 지정 시간까지의 밀리초를 숫자로 반환.

🔹Date.UTC<br>
new Date(year, month,[day, hour, minute, second, milisecond])와 같은 형식의 인수를 사용해야한다. Date.UTC메서드의 인수는 로컬 타임이 아닌 UTC로 인식된다.

🔹Date.prototype.getFullYear<br>
Date 객체의 연도를 나타내는 정수를 반환한다.

🔹Date.prototype.setFullYear<br>
Date 객체에 연도를 나타내는 정수를 설정한다. 연도 이외 옵션으로 월, 일도 설정할 수 있다.

🔹Date.prototype.getMonth<br>
Date 객체의 월을 나타내는 0 - 11 정수를 반환한다. 1월은 0, 12월은 11이다.

🔹Date.prototype.setMonth<br>
Date 객체에 월을 나타내는 0 - 11 정수를 설정한다. 월 이외 옵션으로 일도 설정할 수 있다.

🔹Date.prototype.getDate<br>
Date 객체의 날짜(1-31)을 나타내는 정수를 반환한다.

🔹Date.prototype.setDate<br>
Date 객체에 날짜(1-31)를 나타내는 정수를 설정한다.

🔹Date.prototype.getDay<br>
Date 객체의 요일(0-6)을 나타내는 정수를 반환한다.

🔹Date.prototype.getHours<br>
Date 객체의 시간(0-23)을 나타내는 정수를 반환한다.

🔹Date.prototype.setHours<br>
Date 객체에 시간(0-23)을 나타낸느 정수를 설정한다.

🔹Date.prototype.getMinutes<br>
Date 객체의 분(0-59)을 나타내는 정수를 반환한다.

🔹Date.prototype.setMinutes<br>
Date 객체의 분(0-59)을 나타내는 정수를 설정한다.

🔹Date.prototype.getSeconds<br>
Date 객체의 초(0-59)를 나타내는 정수를 반환한다.

🔹Date.prototype.setSeconds<br>
Date 객체의 초(0-59)를 나타내는 정수를 설정한다.

🔹Date.prototype.getMilliseconds<br>
Date 객체의 밀리초(0-999)를 나타내는 정수를 반환한다.

🔹Date.prototype.setMilliseconds<br>
Date 객체의 밀리초(0-999)를 나타내는 정수를 설정한다.

🔹Date.prototype.getTime<br>
1970년 1월 1일 00:00:00(UTC)를 기점으로 Date 객체의 시간까지 경과된 밀리초를 반환한다.

🔹Date.prototype.setTime<br>
1970년 1월 1일 00:00:00(UTC)를 기점으로 Date 객체의 시간까지 경과된 밀리초를 설정한다.

🔹Date.prototype.getTimezoneOffset<br>
UTC와 Date 객체에 지정된 로캘 시간과의 차이를 분 단위로 반환한다. KST는 UTC에 9시간을 더한 시간이다.

🔹Date.prototype.toDateString<br>
사람이 읽을 수 있는 형식의 문자열로 Date 객체의 날짜를 반환한다.

🔹Date.prototype.toTimeString<br>
사람이 읽을 수 있는 형식의 문자열로 Date 객체의 시간을 표현한 문자열을 반환한다.

🔹Date.prototype.toISOString<br>
ISO 8601 형식으로 Date 객체의 날짜와 시간을 표현한 문자열을 반환한다.

🔹Date.prototype.toLocaleString<br>
인수로 전달된 로캘을 기준으로 Date 객체의 날짜와 시간을 표현한 문자열을 반환한다. 인수 생략시 브라우저가 동작 중인 시스템의 로캘을 적용한다.

🔹Date.prototype.toLocaleTimeString<br>
인수로 전달한 로캘을 기준으로 Date 객체의 시간을 표현한 문자열을 반환한다.
