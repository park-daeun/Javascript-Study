## DOM, Document Object Model
- 컴퓨터가 문서를 잘 처리할 수 있도록 문서의 구조를 약속한 것
  - Tree 형태를 따름 : 족보나 가계도와 비슷함
<img src="https://user-images.githubusercontent.com/70877497/137524468-cdc75af7-0bed-4c12-ac60-406b89f05bdf.png" width="50%" height="50%">
<br>

> ### document object
- javascript에서 document로 접근 가능
- children에는 문서의 최상위 엘리먼트인 html이 존재
<br>

> ### Element API
#### 자식, 부모 엘리먼트에 접근하는 방법
- children : 해당 object의 자식 노드에 대한 배열
- parentNode : 부모 노드
- firstElementChild : 첫 자식 엘리먼트
- lastElementChild : 마지막 자식 엘리먼트

#### 같은 레벨의 형제 엘리먼트에 접근하는 방법
- nextElementSibling
- previousElementSibling

<br><br>

## 단일 Element 선택

> ### Document API
#### DOM API를 활용해 문서에서 엘리먼트를 선택하는 방법
- **```document.getElementBy~```** : 단일 엘리먼트를 선택하는 메소드
  - ex) ```document.getElementById 메소드``` : 인자로 HTML element 태그의 id를 전달하면 해당 엘리먼트가 반환됨
- **```document.getElementsBy~```** : 다중 엘리먼트를 선택하는 메소드

<br>

> ### Element API
#### .innerHTML 속성
- 엘리먼트 안의 HTML코드를 변경

#### .innerText 속성
- 엘리먼트 안의 텍스트를 변경

#### .style 속성
- css를 변경 가능

#### getAttribute 메소드
- element의 속성의 값을 얻어옴
- 하나의 인자 : attribute 이름을 받음
- 직접 객체에 동기화되지 않는 속성에 대해서도 접근이 가능
``` javascript
document.getElementById("logo").getAttribute("src");
```

#### setAttribute 메소드
- element의 속성의 값을 설정함
- 두개의 인자 : attribute 이름, 설정할 속성의 값을 받음
- 직접 객체에 동기화되지 않는 속성에 대해서도 값 설정이 가능
``` javascript
document.getElementById("logo").setAttribute("src", "image.png");
```

<br><br>

## 다중 Element 선택
> ### Document API
- **```document.getElementsBy~```** : 다중 엘리먼트를 선택하는 메소드. 배열형태로 값을 반환함

#### document.getElementsByTagName 메소드
- 인자로 HTML element 태그의 이름을 전달하면 해당 엘리먼트들이 반환됨
``` javascript
document.getElementsByTagName("p"); // [<p> ... </p>, <p> ... </p>, ...]
```

#### document.getElementsClassName 메소드
- 인자로 class의 이름을 전달하면, 해당 class의 모든 엘리먼트가 배열로 반환됨
``` javascript
document.getElementsClassName("lyric"); // [<p class = "lyric"> ... </p>, ...]
```

#### document.getElementsByName 메소드
- 인자로 name을 전달하면, 해당 name 속성을 가진 모든 엘리먼트가 배열로 반환됨.
``` javascript
document.getElementsByName("author"); // [<input name="author">, ...]
```
<br>

> ### Element API
#### .value 속성
- input element에 입력된 값은 .value를 통해 얻어올 수 있음
  - getAttribute 메소드로는 받아올 수 없다는 점 주의
``` javascript
a = document.getElementsByName("author")[0];
a.value; // 홍길동 (사용자가 홍길동이라고 입력)
a.value = "이몽룡"; // 이몽룡
a.getAttribute("value"); // null
```
<br><br>

## CSS Selector를 이용한 Element 선택
> ### Document API
- **```document.querySelector```** : css selector를 기반으로 엘리먼트를 선택
  - 조건에 부합하는 element가 여러개인 경우 첫 엘리먼트만 반환.
- ***```document.querySelectorAll```*** : css selector를 기반으로 만족하는 모든 엘리먼트를 선택
``` javascript
document.querySelector("#songWriter"); // <p> ... </p>
document.querySelectorAll("#songWriter"); // [<p> ... </p>, ...]
document.querySelector("p"); // <p> ... </p>
document.querySelectorAll("h1, h2"); // [<h1> ... </h1>, <h2> ... </h2>, ...]
```
<br>

> ### CSS Selector
- ```#``` : name 기반으로 선택
- ```.``` : class 기반으로 선택
- ```,``` : 여러개의 셀렉터를 사용

<br><br>
## Element 추가/삭제
> ### Document API
- ```document.createElement()``` : 문자열 인자로 element tag를 입력하면 해당 엘리먼트가 생성돼 반환됨
``` javascript
hr = document.createElement("hr"); // <hr>
```

<br>

> ### Element API
- ```.appendChild(인자)``` : 추가할 element를 인자로 받아 호출된 element의 자식으로 인자를 추가함
``` javascript
document.body.appendChild(hr);
```
- ```.removeChild(인자)``` : 삭제할 element를 인자로 받아 호출된 element의 자식중에서 해당 element를 삭제
``` javascript
document.body.removeChild(hr);
```
- ```.insertBefore(인자1, 인자2)``` : 인자1로 받은 element를 호출된 element의 자식중 인자2의 이전에 추가함
``` javascript
document.body.insertBefore(hr, document.body.children[3]);
```
- ```.cloneNode()``` : 호출된 element를 복사해서 반환함
``` javascript
hr2 = hr.cloneNode(); // <hr>
```
