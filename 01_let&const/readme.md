# let & const

선행학습 필요 Javascript scope, hoisting, excution context

## let과 const

- ES6 표준에서 처음으로 추가된 특징
- ES6에서는 변수와 상수를 구분
- let 으로 선언된 변수는 다시 선언 불가
- const는 선언하면서 초기화 필수

원시형에서 변수는 let, 상수는 const

var는 재할당이 가능하지만 let과 const는 한번 선언한 변수는 다시 선언할 수 없음.

let은 초기값을 할당하지 않으면 undefined

const 객체의 프로퍼티는 변경 가능

    const animal = {
        name: 'cat',
        weight: 5
    };
    animal.name = 'dog';
    console.log(animal);    // name: 'dog', weight: 5
    
## Block scope

- Block-scope : {}로 감싸진 유효 범위
- 기존의 var는 function scope레벨 hoisting
- let 키워드를 사용해 변수의 유효범위를 블록 스코프 처리

스코프는 변수의 유효범위

    var num = 1;
    function printNum(){
        console.log(num);
        var num = 2;
        console.log(num);
    };
    printNum();
    
    // 실행 결과 : undefined, 2
    
Hoisting : var, let, function 등 모든 선언문이 끌어올려져 해당 변수가 속한 스코프의 최상단으로 올려져 버리는 현상.

    var product = 'phone';
    if(true){
        var product = 'tv';
        console.log(product)
    };
    console.log(product);
    
    // 실행결과 : tv tv
    
let 사용시

     let product = 'phone';
     if(true){
        var product = 'tv';
        console.log(product)
     };
     console.log(product);
     
     // 실행결과 : tv phone
     
let 사용시 블록 스코프와 전역 스코프로 분리됨