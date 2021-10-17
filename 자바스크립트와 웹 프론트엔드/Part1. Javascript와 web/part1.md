## HTML, CSS, JS
- **HTML** : 웹 페이지의 ```구조```를 나타냄
- **CSS** : 웹 페이지 안에 존재하는 요소들의 ```스타일```을 나타냄
- **JS*** : JS로직을 통해 문서의 구조와 스타일에 ```변화```를 줄 수 있음
  - 브라우저에서는 Javascript에서 HTML, CSS에 접근할 수 있는 API를 제공함(document, window...)
  
<br><br>
  
## Window Object
- **Javascript 실행시 가장 상위에 존재하는 객체**
  - 변수를 선언하거나 함수 선언시 window 객체안에 선언됨
  ``` javascript
  a; // a
  window.a; // a
  
  function b(){console.log("b")}
  b(); // b
  window.b(); // b
  ```
<br>

- **표시된 웹 페이지의 정보에 접근하거나 변경을 할 수 있음**
  - ```window.location``` : 현재 브라우저 창의 주소를 나타내는 객체
  - ```window.location.href``` : 브라우저 창에 입력된 주소, 변경 가능
  - ```window.navigator``` : 브라우저 자체에 대한 정보
  - ```window.screen``` : 디스플레이의 사이즈
  - **```window.document```** : 웹 페이지 문서의 HTML, CSS 등에 대한 접근 가능
    - ```document.body; document.head; document.stylesheet; ...```

<br><br>

## CSS 다루기
> #### Cascading Style Sheet
- HTML 문서의 요소가 어떻게 표시될지 정의

<br>

> #### 문법
```[selector] { [property_name]:[value]; ... }```
- selector : tag이름, id, class로 작성 가능
  - tag이름 : 태그 이름 그대로 사용(h1, h2, p, img, ...)
  - id : #을 붙이고 id 사용(#name, #id, ... )
  - class : .을 붙이고 class 이름 사용 (.lyric, ...)
- property_name : selector에 해당하는 엘리먼트의 style 속성
- value : 앞에 정의한 style property의 값

<br>

> #### 적용하기
1. head 태그 안에 <link> 태그 사용
``` html
<link rel="stylesheet" href="[css file]">
```

2. head 태그 안에 <style> 태그를 사용해 직접 정의
``` html
<style>
       ...
</style>
```

3. html element안에 직접 속성으로 정의
``` html
<p style="color:red">...</p>
```

<br>

> #### CSS 적용 우선순위
1. html element 안에서 적용한 스타일
2. style tag안에서 적용한 스타일
3. link를 통해 외부 파일에서 적용한 스타일
