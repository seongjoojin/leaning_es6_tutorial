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