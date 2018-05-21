# Iterator & for-of

새로운 종류의 루프 문법 iterator 와 for-of 키워드 추가

    const myArray = [10,20,30];
    
    for(let value of myArray){
        console.log(value);
    }
    
    //  실행결과
    10
    20
    30
    
# iterable

iterable 객체는 순환 가능.

iterable 객체는 Symbol.iterator 속성을 가진다.


이터레이터는 이터러블 객체를 말하는 것

이터러블 객체는 순회를 위해 Symbol.iterator 속성을 가지고 있음.