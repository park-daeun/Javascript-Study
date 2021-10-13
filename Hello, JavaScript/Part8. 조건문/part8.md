## if문

> #### if, else if, else
``` javascript
if(/*조건식*/){
    /*참인경우 실행될 코드*/
}
else if( /*조건식*/ ){
    /*if 문의 조건이 거짓이고, 위의 조건식이 참인경우 실행될 코드*/
}
/* 여러개의 else if... */
else if( /*조건식*/ ){
    /*위의 if, else if문의 모든 조건이 거짓이고, 위의 조건식이 참인경우 실행될 코드*/
}
else{
    /*모든 if, else if 문이 모두 실행되지 않았을 때 실행될 코드*/
}
```

<br><br>

## switch문
#### switch, case
조건에 따라 프로그램의 흐름을 분기해서 특정 코드가 실행되도록 함
``` javascript
switch( /*비교할 값*/ ){
    case /*값1*/:
        /*비교할 값이 값1인 경우 실행될 코드*/
        break;
    case /*값2*/:
        /*비교할 값이 값2인 경우 실행될 코드*/
        break;

    /*
    ... 여러개의 case
    */

    default:
        /*비교할 값이 위의 모든 값과 다른 경우 실행될 코드*/
        break;
}
```
<br>

#### break
break구문을 만나면, switch-case 문의 마지막 중괄호(}) 밖으로 빠져나옴.
- break를 사용하지 않으면, switch문에서 빠져나오지 않고 다음 case에 해당하는 코드까지 실행됨.
