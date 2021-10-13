## while문
> #### while
조건이 만족하는 동안 반복실행될 코드를 계속 실행
``` javascript
while( /*조건식*/ ){
    /* 반복 실행될 코드 */
}
```
<br>

> #### continue, break;
- continue : 남은 반복실행될 코드를 모두 skip
- break : 반복문에서 즉시 탈출

<br><br>

## do while문
한번은 코드가 실행되고, 이후에 반복실행될지 말지를 결정
``` javascript
do{
    /* 반복 실행될 코드 */
}while( /*조건식*/ );
```
<br>

#### 조건식이 거짓(False) 일 때,
- while : 한번도 실행되지 않음
- do, while : 한번은 실행되고 종료

<br><br>

## for문
초기구문, 업데이트 구문, 반복조건 을 한 구문에 합친 반복문.

#### 0~4까지 더하는 동일한 while문과 for문.
- while 문
``` javascript
var sum = 0;
var i = 0; //초기 설정 코드
while( i < 5 /*조건식*/ ){
    sum = sum + i;
    i++; // 업데이트 코드
}
```
- for문
``` javascript
var sum = 0;
for( var i = 0 ; i < 5 ; i++ ){
    sum = sum + i;
}
```

<br><br>

## for in문
객체의 각 엘리먼트에 접근할 수 있는 반복문.

#### 객체의 속성들을 출력하는 동일한 코드
- for 구문 사용
``` javascript
var obj = {name:"object", weight:30, isObject:true, arr:[1,2,3], obj:{property:1}};
var property_list = Object.keys(obj); // ['name', 'weight', 'isObject', 'arr', 'obj']

for( var i=0 ; i<property_list.length ; i++ ){
    var propertyName = property_list[i];
    console.log( "\t", propertyName, ": ", obj[propertyName] );
}
```
- for in 구문 사용
``` javascript
var obj = {name:"object", weight:30, isObject:true, arr:[1,2,3], obj:{property:1}};

for( var propertyName in obj ){
    console.log( "\t", propertyName, ": ", obj[propertyName] );
}
```
