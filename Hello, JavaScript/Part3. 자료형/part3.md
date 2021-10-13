## 기본 자료형

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

> #### string Type: 문자열
``` javascript
var c="안녕하세요", d="a";
```
``` javascript
var a='문자열은 따옴표로 둘러싸면 됩니다.';
var b="큰따옴표로도 문자열을 표현할 수 있습니다.";

var c="큰따옴표 문자열에는 따옴표 '를 사용할 수 있습니다.";
var d='따옴표 문자열에는 큰따옴표 "를 사용할 수 있습니다.';

var e="따옴표를 쓰고 싶다면 \'이렇게\' 사용하면 됩니다. 마찬가지로 \"큰따옴표\"도 쓸 수 있습니다.";
var f='따옴표를 쓰고 싶다면 \'이렇게\' 사용하면 됩니다. 마찬가지로 \"큰따옴표\"도 쓸 수 있습니다.';

var g="\\ 문자를 쓰고 싶다면 역슬래시를 두번 씁니다.";

var h="문자열에서 줄바꿈을 하고 싶다면, \n 역슬래시n을 사용합니다.";

var i=a+b; // 문자열은 따옴표로 둘러싸면 됩니다.큰따옴표로도 문자열을 표현할 수 있습니다.

var j="abcde";
```
- 따옴표나('), 큰따옴표(")로 감싸서 문자열 표현
- 문자열 안에 따옴표, 큰따옴표 등의 문자를 활용하려면 escape character를 활용
  - escape character는 역슬래시(\)로 사용
  - 줄바꿈 : \n
  - 따옴표 : \'
  - 큰따옴표 : \"
  - 역슬래시 : \\

<br>

> #### boolean Type: 맞다/틀리다를 표현
``` javascript
var e = true, f = false;
```

<br><br>

## Object

> #### Object
- number, string, boolean의 단순 자료형보다 더 복잡한 자료를 표현할 때 사용

<br>

> #### 객체를 만드는 법
- 중괄호 {} 를 사용해 정의 가능
- 객체는 속성의 집합으로 이뤄짐
  - 각 속성은 이름과 값으로 이뤄짐
  - 객체 정의 시 속성이름:값의 형태로 속성 정의 가능
  - 속성의 값은 모든 자료형이 가능, object 포함
``` javascript
var man = {name: "홍길동", age:20, height:100}
```

<br>

> #### 객체의 속성에 접근하는 법
- 객체 이름 뒤에 점(.)을 사용하고 속성 이름에 접근 할 수 있음
- 객체 이름 뒤에 대괄호([]) 안에 속성 이름을 문자열로 접근할 수 있음
``` javascript
man.name = "이몽룡"
man["height"] = 180
```

<br><br>

## undefined와 null

> #### undefined
- 시스템에서 어떤 변수나 속성이 정의되지 않은 경우를 표현하기 위해 사용
  - 선언만 하고 초기화가 되지 않는 변수의 타입이나 값
  - 객체의 정의되지 않은 속성의 타입이나 값

<br>

> #### null
- 개발자가 명시적으로 아무것도 없는 비어있는 상태를 나타낼 때 사용
  - typeof의 결과는 object이며 값은 null
