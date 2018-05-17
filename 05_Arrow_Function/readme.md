# Arrow Function & this

## 화살표 함수

익명 함수를 간략하게 표현 할 수 있는 화살표 표현식

    const myFunction = ()=>{
        console.log("ES6 arrow")
    }
    myFunction();
    
    //  실행결과
    ES6 arrow function
    
화살표함수는 실행문이 하나라면 중괄호도 생략가능!

    const myFunction = ()=>console.log("ES6 arrow");
    myFunction();

## 함수 실행에서의 this

콜백 함수를 정의할 때 쉽게 컨텍스트 활용

웹 브라우저에서는 window객체 = 전역 객체

ES5에서는 call 또는 apply 함수를 이용해 this를 지정해주는 방법을 사용하곤 함 ( this binding )

화살표 함수 표현식은 표현 방법만 달라진 것이 아니라 this도 다르므로 기존과 다른 결과가 나옴

# IIFE

## 즉시 실행 함수

Immediately-invoked function expression

    (function(lang){
        console.log(lang);
    }("ES5"));
    
    // 실행결과
    ES5
    
화살표함수로 바꾸면!

     ((lang)=>{
        console.log(lang);
     })("ES6");
     
     // 실행결과
     ES6
     
즉시 실행 함수는 한번의 실행만 필요로 하는 초기화 코드 부분에 많이 사용됩니다.

# 정리하기

function 키워드를 생략하고 괄호와 화살표 사용.

화살표 표현식 익명함수는 콜백 함수를 할당한 당시의 컨텍스트 활용

즉시실행함수를 사용할 때는 괄호를 먼저 묶고 함수를 호출