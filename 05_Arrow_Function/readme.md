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