# Promise & then

Promise - 비동기 처리를 좀 더 쉽게 하기 위해 언어적 차원에서 지원하는 특징

    const promise = new Promise(function(resolve, reject){
        // 비동기 처리 작성
        // 처리가 끝나면 resolve 또는 reject를 호출합니다.
    });
    
then() - then메서드에 두 개의 인자는 resolved/rejected 상태값을 받아 처리하는 콜백함수

    const promise = new Promise(function(resolve,reject){
       console.log("Promise");
       resolve()
    });
    promise.then(function(){
        console.log("Resolved")
    });
    console.log("Hi");
    
    // 실행결과
    Promise
    Hi
    Resolved
    
then 예제 2

    const pro2 = new Promise(function(resolve, reject){
       reject("rejected!");
    });
    pro2.then(function(contens){
        console.log(contents);
    }, function(err){
        console.error("err: " + err)
    });
    
    // 실행결과
    err: rejected!
    
프로미스는 입력이 정상적으로 처리되면 이행(fulfilled)되었다고 합니다.
실패되었다면 거절(rejected) 되었다고 함.

then 메서드를 사용하면 수행 뿐만아니라 거절 핸들러를 할당할 수 있음.

