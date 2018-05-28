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
    
