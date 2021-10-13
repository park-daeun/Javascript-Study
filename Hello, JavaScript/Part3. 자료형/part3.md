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