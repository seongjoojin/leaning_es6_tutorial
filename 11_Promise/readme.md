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
    console.log("")