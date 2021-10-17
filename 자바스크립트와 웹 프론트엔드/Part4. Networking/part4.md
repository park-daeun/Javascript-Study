## AJAX(Asynchronous Javascript And XML)
- 브라우저에서 페이지를 이동하지 않고 자바스크립트를 통해 HTTP Request를 보내고 받아 JS에서 처리할 수 있음
- 사용자에게 더 나은 사용 경험 제공, 대부분의 웹사이트에서 사용되고 있는 기술
<br>

> ### AJAX - Request 보내기
#### 1. JAX를 위한 객체 생성
``` javascript
var req = new XMLHttpRequest(); // HTTP 요청을 만들 수 있는 새로운 객체를 생성하는 명령
```

#### 2. 요청의 방식과 URL 설정
``` javascript
req.open("GET", "./data.txt"); // http request method와 URL 설정
```

#### 3. 요청 전송
``` javascript
req.send();
```

#### 응답 확인
- req.response에 저장됨
- 비동기 방식으로 요청하기 때문에 send 메소드 호출 후, 바로 코드에서 접근하면 데이터가 비어 있음
- AJAX의 진행에 따라 호출되는 callback함수를 활용해야 함.
<br>

> ### AJAX - Response 받아서 처리하기
#### readyState 속성
- AJAX 요청에 따라 0~4까지 변화함

readyState|의미
:---:|---
0|open 메소드 호출 전
1|open 메소드 호출 후, send 메소드 호출 전
2|보낸 요청에 대해 응답 헤더가 수신된 후
3|응답의 바디 부분이 수신중일 때
4|모든 응답이 수신되었을 때
<br>

#### onreadystatechange 속성
- readyState가 변할 때마다 호출되는 콜백 함수
<br>

#### status 속성
- HTTP response의 응답 헤더에 기록된 코드

Response|Code	의미
:---:|---
200|OK
404|Not Found
500|Internal Error
...|...
<br>

#### 응답을 정상적으로 수신한 경우
- readyState : 4
- status : 200
<br>

#### 기타 callback function 활용 가능한 속성
- onloadstart
- onprogress
- onabort
- onerror
- onload
- ontimeout
- onloadend
<br><br>

## JSON(Javascript Object Notification)
- 자바스크립트의 객체를 문자열로 표현하는 방법
  - 프로그램간에 전달하기 편리 (서버 -> 브라우저)
<br>

> ### JSON API
- **```JSON.stringify( object )```**
  - 인자로 받은 객체를 JSON 문자열로 반환함
- **```JSON.parse( sring )```**
  - 인자로 받은 문자열을 Javascript Object로 변경해 반환함
``` javascript
var original_obj = { pi:3.14, str:"string" };

var json_str = JSON.stringify( original_obj );
// 반환 문자열 : "{"pi":3.14,"str":"string"}"

var parsed_obj = JSON.parse( json_str );

console.log( original_obj ); // {pi: 3.14, str: "string"}
console.log( parsed_obj ); // {pi: 3.14, str: "string"}
```
- undefined, function 은 변환되지 않음에 주의!
<br><br>

## AJAX + JSON
- AJAX를 통해 JSON 데이터를 받아옴
``` javascript
var req = new XMLHttpRequest();

req.onreadystatechange = function(){
    if( this.readyState == 4 ){
        // ...
    }
}

req.open("GET", JSON_DATA_URL);
req.send(); 
```
- JSON.parse API를 이용해 받아온 JSON 문자열 데이터를 Javascript 객체로 변환
``` javascript
req.onreadystatechange = function(){
    if( this.readyState == 4 ){
        data = JSON.parse(this.response);
        //...
    }
}
```
- 데이터를 처리하는 Javascript 프로그램 실행 (HTML 문서에 반영)
  - 데이터가 여러개인 경우 (배열 형태로 값을 받은 경우) 반복문으로 각각의 데이터에 대해 처리
``` javascript
for( var i = 0 ; i < data.length ; i++ ){
    document.write(data[i].id, data[i].msg);
}
```
