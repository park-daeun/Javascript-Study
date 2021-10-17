## Callback Function
- 조건을 등록해 두고 그 조건을 만족한 경우, 나중에 호출되는 함수
<br>

> ### 시간을 기반으로 콜백함수를 호출하는 명령
#### setTimeout( function, time )
- time 시간이 지난 경우 function 함수를 콜백하는 함수
- time 은 millisecond (1/1000초) 단위
- timerId를 반환함
``` javascript
function callback() { 
  console.log("callback function is called.");
}

setTimeout(callback, 3000); // 1 이 반환되고 3초 뒤에 "callback function is called." 출력
```
<br>

#### clearTimeout( timerId )
- setTimeout 함수 호출의 결과로 반환된 timerId를 인자로 받아 예약되어 있던 function호출을 취소
  - 이미 function이 호출된 경우(시간이 지나 이벤트가 발생한 경우)에는 효과 없음
<br>

#### setInterval( function, time )
- time 시간이 경과할 때마다 function 함수를 콜백하는 함수
- timerId를 반환함
``` javascript
setInterval(callback, 5000); // 2 가 반환되고 5초마다 "callback function is called." 출력
```
<br>

#### clearInterval( intervalId )
- setInterval 함수 호출의 결과로 반환된 intervalId를 인자로 받아 주기적으로 호출되던 function 호출을 취소
``` javascript
clearInterval(2); // 5초마다 callback 호출하던 거 멈춤
```
<br><br>

## HTML Tag 속성에 EventHandler 추가하기
> ### 브라우저에서 발생하는 Event 종류
- ***form event*** : HTML 문서의 form element에 변화가 생기거나 submit버튼을 누르는 경우 등의 상황에서 발생
- ***window event*** : 패이지가 모두 로드되었을 때 발생하는 onload event 등이 있음
- ***mouse event*** : 사용자가 마우스를 조작했을 때 발생
- ***key event*** : 사용자가 키보드를 조작했을 때 발생
<br>

> ### Event
- ```click``` : mouse event로 HTML element를 마우스로 클릭한 경우 발생
- ```change``` : form event로 form 엘리먼트의 내용이 변경된 경우 발생
- ```keydown``` : key event로 key가 눌린 경우 발생
<br>

> ### HTML Tag의 속성으로 Event Handler 추가
- Tag 의 속성에 event handler 코드를 추가
  - ***onEvent*** 속성 사용 ( onclick, onchange, onkeydown, ... )
``` html
 <h1 onclick="console.log('clicked');">..</h1>
 <input type="text" onchange="console.log('changed');" onkeydown="console.log('typed');">
```
<br><br>

## JS에서 EventHandler 설정
> ### Event
- ```submit``` : form 태그의 submit 이벤트
  - EventHandler에서 return false 시 브라우저 자체 기능 (페이지 이동) 비활성
- ``` keydown``` : 키를 누른 경우 발생하는 이벤트
  - EventHandler에서 return false 시 키 입력 비활성
  - 실제로는 keydown event -> keypress event -> keyup event 순으로 이벤트가 발생하며 keypress event 발생시에 키가 입력됨. keydown event 에서 return false를 한 경우 keypress event가 이어서 발생하지 않음.
<br>

> ### EventHandler 설정
#### property에 직접 Handler설정
- Element의 ```"on"+"이벤트"``` 의 속성에 메소드를 직접 지정
``` javascript
document.getElementById("form1").onsubmit = function eventHandler(){
    console.log("from property");
    return false; // 브라우저의 submit 처리 비활성
}
```
<br>

#### addEventListner 메소드
- element의 addEventListener(이벤트, 함수) 메소드를 호출해, eventHandler 등록
  - 여러개의 이벤트 핸들러를 등록할 수 있음
``` javascript
document.getElementById("form1").addEventListener(
    "submit", 
    function eventHandler(){
        console.log("from addEventListener");
        return false;
    }
);
```
<br>

#### removeEventListener 메소드
- element의 removeEventListener(이벤트, 함수) 메소드를 호출해, eventHandler 삭제
<br>
