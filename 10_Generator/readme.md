# Generator

function* 키워드로 정의하는 제네레이터 함수는 Generator 객체를 반환.

Generator 객체는 iterable 한 iterator 객체.

함수의 끝부분까지 모두 수행된 이후, generator 함수에서 return 사용, 에러 발생 이렇게 3가지 경우 종료.

# yield

yield 구문은 제너레이터의 실행을 멈췄다가 다음에 다시 이어서 시작

    function* intro(name){
        console.log("환영합니다");
        yield name + "님 안녕하세요";
        yield "Apple 지원에 오신것을 환영합니다";
        yield "도움이 필요하시면 언제든지 문의하십시오";
        yield "다음에 또 만나요";
    }
    let iter = intro("jack");
    console.log(iter.next());
    console.log(iter.next());
    console.log(iter.next());
    console.log(iter.next());
    console.log(iter.next());
    
    // 실행결과
    
    환영합니다
    { value:  "jack님 안녕하세요", done: false }
    { value:  "Apple 지원에 오신것을 환영합니다", done: false }
    { value:  "도움이 필요하시면 언제든지 문의하십시오", done: false }
    { value:  "다음에 또 만나요", done: false }
    { value:  undefined, done: true }
    
# yield*

yield* iterable 을 사용하면 해당되는 iterable의 값들을 순차적으로 반환

    function* myGenFn(){
        yield* [1,2,3,4,5,6,7];
        yield 8;
        yield 9;
    }
    
    let iterator = myGenFn();
    
    for(const n of iterator){
        console.log(n);
    }
    
    // 실행결과
    1
    2
    3
    4
    5
    6
    7
    8
    9
    
# next(value)

다음 값을 얻는 역할의 메서드.

매개변수는 바로 이전의 yield(expression)의 반환값으로 사용

    function* foo(){
        console.log(yield);
        console.log(yield);
        console.log(yield);
    }
    let iter = foo();
    iter.next();
    iter.next(1);
    iter.next(2);
    iter.next(3);
    
    // 실행결과
    1
    2
    3
    
제너레이터 함수가 값을 쓰고, 제네레이터 객체의 이터레이터 인터페이스로 값을 읽는 것 뿐만 아니라 제너레이터 객체에 값을 쓰고 제너레이터 함수가 값을 읽어 갈 수도 있음

# return(value)

매개변수로 온 값을 value로 반환하고, Generator를 종료

    function* gen(){
        yield 1;
        yield 2;
        yield 3;
    }
    
    let g = gen();
    
    console.log(g.next());
    console.log(g.return("foo"));
    console.log(g.next());
    
    // 실행결과
    { value: 1, done: false }
    { value: 'foo', done: true }
    { value: undefined, done: true }
    
# throw(exception)

인자로 받은 에러 발생시키고, Generator를 종료

    function* generator(){
        try{
            yield 'foo';
        }
        catch(err){
            console.log(err.message);
        }
    }
    
    let iterator = generator();
    
    let foo = iterator.next();
    console.log(foo.value);
    
    let nextThing =  iterator.throw(new Error('bar'));
    
    // 실행결과
    foo
    bar