# Template Literals

## 표현식과 템플릿 문자

- 백틱(backtick)문자 `를 사용
- 템플릿 문자열 표현식 처리

 기존 es5 방식
 
    var number = "one = " + "1" + "\ntwo = " + "2";
    console.log(number);
    
    // 실행결과 
    one = 1
    two = 2
    
ES6 방식1

    let name = "jack";
    let weight = 60;
    
    console.log(`
        name = ${name}
        weight = ${weight}
        weight + bagWeight = ${weight + 3};
    `);
    
    // 실행결과 
    name = jack
    weight = 60
    weight + bagWeight = 63;
    
ES6 방식2(함수 호출도 가능)

    let list = {1, 2, 3, 4, 5, 6, 7, 8};
    let num = list.filter (function (n){
        return n%2===0;
    });
    console.log(`
    num = ${num}
    `);
    
    // 실행결과
    
    num = 2, 4, 6, 8
    
## 정리하기

- 백팩 내에 multi-line string 을 입력
- 템플릿 문자열의 표현식을 통해 변수를 입력