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
    
## iterable

iterable 객체는 순환 가능.

iterable 객체는 Symbol.iterator 속성을 가진다.


이터레이터는 이터러블 객체를 말하는 것

이터러블 객체는 순회를 위해 Symbol.iterator 속성을 가지고 있음.

# Symbol

객체에 다른 어떤것과 다른 유니크한 속성을 만들기 위한 타입

typeof가 반환하는 타입

- Undefined
- Boolean
- String
- Number
- Object
- Function
- Symbol


    let name = Symbol("kim");
    console.log(typeof name);
    
    // 실행결과
    symbol
    
typeof null 은 object 로 출력됨

    예제2
    
    const myObject = {
        symbol1: [Symbol("My Symbol")],
        symbol2: [Symbol("My Symbol")]
    };
    console.log(myObject.sysmbol1 == myObject.sysmbol2);
    
    // 실행결과
    false
    
Symbol 의 가장 큰 특징은 고유한 것!

    const myObject = {};
    
    myObject.a = "apple";
    myObject["b"] = "book";
    
    let c = Symbol("c");
    myObject[c] = "cat";
    myObject[Symbol("d")] = "dog";
    
    for(let key in Object){
        console.log("key in : " + key);
    }
    console.log("Object.keys(myObject)" + Object.keys(myObject));
    console.log("myObject[c]: + myObject[c]");
    console.log(Object.getOwnPropertySymbols(myObject));
    
    //  실행결과
    Object.keys(myObject) : a,b
    myObject[c] : cat
    [Symbol(c), Symbol(d)]
    
for-in , Object.keys 메소드는 심볼을 출력하지 않음.

Object.getOwnPropertySymbols 메소드를 통해 객체 안에 존재하는 심볼 키 목록을 조회할 수 있음.

Symbol.iterator 속성을 가지고 있으면 iterable 객체 