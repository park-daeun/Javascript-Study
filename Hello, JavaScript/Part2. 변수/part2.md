## 변수

> #### 변수
``` javascript
var a;
a = 10;

var b, c; // 여러 변수 동시에 선언 가능
var d=20, e=30; // 여러 변수 동시에 초기화 가능
```

<br>

> #### prompt() 명령어
- promprt 뒤에 따라오는 괄호 안에 들어있는 메세지를 사용자에게 보여주고, 문자열을 입력받는 명령
  - 변수에 값을 저장하는 구문과 함께 사용해서, 사용자가 입력한 값을 변수에 저장 가능
``` javascript
var name=prompt("이름을 입력해 주세요");
```

<br>

> #### 변수의 값 활용
``` javascript
var name = prompt("이름을 입력해주세요.");

console.log(name + "님 환영합니다."); // 박다은님 환영합니다.
console.log(name, "님 환영합니다."); // 박다은 님 환영합니다.

alert(name + "님 환영합니다.");
```

<br>

## 자료형

> #### number Type: 숫자
- 64bit로 실수와 정수 모두 표현 가능
- 정상적이지 않는 숫자나 표현할 수 없는 범위의 수를 표시하는 NaN, Infinity
``` javascript
var a=100, b=3.14;
```
- string to num: parseInt, parseFloat
``` javascript
var height = prompt("키를 입력해주세요");
console.log(height, typeof(height));

var height_int = parseInt(height);
console.log(height_int, typeof(height_int))

var heihg_float = parseFloat(height);
console.log(heihg_float, typeof(heihg_float))
```

<br>