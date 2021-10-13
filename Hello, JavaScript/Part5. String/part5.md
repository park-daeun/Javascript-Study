## String

> #### 문자열 길이 알아내기
- 문자열의 ```.length``` 속성을 이용
  - ```str.length```
``` javascript
var str = "Hello";

str.length // 5
str["length"] // 5
```

<br>

> #### 문자열 붙이기
- ```.concat``` 함수 사용
  - ```str1.concat(str2)```
``` javascript
var str = "Hello";
var str2 = " World";
str.concat(str2); // "Hello World"

var str3 = str.concat(str2);
str3; // "Hello World"

str.concat(str2).concat("!"); // "Hello World!"

"Hello".concat(" World").concat("!"); // "Hello World!"
```
<br>

- 더하기(+) 연산자 사용
  - ```str1+str2```
``` javascript
var str = "Hello";
var str2 = " World";

str + str2 // "Hello World"
"Hello"+" World"+"!" // "Hello World!"

"pi is " + 3.14 // "pi is 3.14"
3.14 + " is pi" // "3.14 is pi"
```

<br>

> #### 특정 위치의 문자열 알아내기
- ```.charAt``` 함수 이용
  - 첫 문자 : ```str.charAt(0)```
  - 마지막 문자 : ```str.charAt(str.length-1)```
  
- 대괄호([]) 사용
  - 첫 문자 : ```str[0]```
  - 마지막 문자 : ```str[str.length-1]```

``` javascript
var str = "abcdeabcde";

str.charAt(0); // "a"
str.charAt(9); // "e"
str.charAt(10); // ""
str.charAt(-1); // ""

str[1]; // "b"
str[10]; // undefined
str[-1]; // undefined
```

<br>

> #### 부분문자열 구하기
문자열의 연속된 일부분을 구하는 함수
- ```.substring(pos1, pos2)``` : pos1 에서 pos2까지의 부분 문자열 반환
  - pos2 생략시 pos1에서부터 마지막 까지의 문자열 반환
- ```substr(pos, length)``` : pos에서 length길이 만큼의 부분 문자열 반환
  - length 생략시, pos에서 마지막까지의 문자열 반환
  - pos 가 음수인 경우, ```str.length - pos``` 로 동작
``` javascript
var str = "abcdeabcde";

str.substring(2,4); // "cd"
str.substring(2); // "cdeabcde"

str.substr(2,4); // "cdea"
str.substr(2); // "cdeabcde"
str.substr(-7); // "deabcde"
str.substr(-7, 2); // "de"
```

<br>

> #### 문자열 검색하기
- indexOf(str)
- lastIndexOf(str)
``` javascript
var str = "abcdeabcde";

str.indexOf("bc"); // 1

str.lastIndexOf("bc"); // 6
str.lastIndexOf("f"); // -1
```
