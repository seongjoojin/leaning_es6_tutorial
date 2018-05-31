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

# chaining & catch

chaining - 여러개의 프로미스를 연결.

    let promise = new Promise(function(resolve,reject){
        resolve(1);
    })
    
    promise.then(function(value){
        return value + 9;
    })
    .then(function(value){
        return value * 2;
    })
    .then(function(value){
        return value / 4;
    })
    .then(console.log);
    
    // 실행결과
    5
    
catch() - 거절 핸들러만 할당. 프로미스가 거부된 경우 무엇을 할지 정의.

    const promise = new Promise(function(resolve,reject){
        resolve();
    })
    
    promise.then(function(){
        throw new Error("Error in then()");
    }).catch(function(err){
       console.log("then error : ", err);
    });
    
    // 실행결과
    
    then error :  Error: Error in then()
    
# all

all() - 모든 프로미스를 성공하면 resolve, 아닌 경우 reject

    const pro1 = (param)=>{
        return new Promise((resolve, reject)=>{
            param ? resolve("여행1") :  reject("거부")
        });
    };
    
    const pro2 = (param)=>{
        return new Promise((resolve, reject)=>{
            param ? resolve("여행2") : reject("거부2");
        });
    };
    
    Promise.all([pro1(true),pro2(true)]).then((value)=>{
        console.log("all프로미스 값 " + value)
    });
    
    // 실행결과
    
    all프로미스 값 여행1,여행2
    
예제2

    const pro1 = new Promise(function(resolve,reject){
        resolve(10);
    });
    const pro2 = new Promise(function(resolve,reject){
        reject(20);
    });
    const pro3 = new Promise(function(resolve,reject){
        resolve(30);
    });
    const pro4 = Promise.all([pro1,pro2,pro3]);
    pro4.catch(function(value){
      console.log(Array.isArray(value));
      console.log(value);  
    });
    
    // 실행결과
    false
    20
    
# 정리하기

Pending(대기), Fulfilled(이행), Rejected(거부)

then() - 메서드 수행 및 거절 핸들러 할당

catch() - 메서드를 사용하면 거절 핸들러만 할당