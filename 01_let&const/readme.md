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

## Temporal Dead Zone

let, const는 TDZ에 의해 제약

    let product = 'phone';
    if(true){
        // 변수 product에 대한 tdz가 시작
        console.log(product);
        var product = 'tv';     // 선언문은 변수 product에 대한 tdz를 종료
    };
    console.log(product);
    
let은 var와 달리 변수가 초기화 되기 전에 접근하면 ReferenceError(참조에러)가 발생함<br>
var는 선언과 동시에 초기화가 되지만 let은 먼저 변수가 스코프에 선언은 되지만 초기화가 한번에 이루어지지 않고 선언문에 도달해야 이루어지기 때문임.

이와 같이 let으로 선언된 변수가 초기화 되기 전에 엑세스 할수 없는 구역을 Temporal Dead Zone 줄여서 TDZ라고 함.

## 정리하기

- let은 변수의 유효범위가 블록스코프
- 원시형은 변수는 let, 상수는 const
- 참조형은 const