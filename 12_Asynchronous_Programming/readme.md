# 비동기 프로그래밍

비동기 프로그래밍을 위한 강력한 도구 제네레이터와 프로미스

# 콜백 지옥

콜백 함수를 연속사용으로 발생

콜백함수를 다른 함수로 전달하는 순간 그 콜백함수는 제어권 상실

    $.get('url', function (response) {
        userValidator(response, function (data){
            userRegister(id, function (data){
                userDisplay(result, function (data){
                    console.log(text);
                });
            });
        });
    });
    
# 각각의 함수로 구분

코딩 패턴으로 콜백함수 분리

    function validator() { /* - */ }
    function register(user) { /* - */ }
    function display(user) { /* - */ }
    
    function greeting() {
        const user = validator();
        register(user);
        display(user);
    }
    
# Promise

프로미스로 비동기 처리

    function validator() { /* - */ }
    function register(user) { /* - */ }
    function display(user) { /* - */ }
    
    function greeting(input) {
        return validator()
            .then(user => register())
            .then(user => display());
    }
    
# Generator

제너레이터로 비동기 처리
    
    function validator() { /* - */ }
    function register(user) { /* - */ }
    function display(user) { /* - */ }
    
    const myGenerator = function* () {
        const user =  yield validator()
        yield register(user);
        yield display(user);
    };
    
# Generator와 Promise를 결합

    const validator= () => { return new Promise(...) }; 
    const register= () => { return new Promise(...) }; 
    const display= () => { return new Promise(...) }; 
    
    const myGenerator = function* () {
        const user =  yield validator()
        yield register(user);
        yield display(user);
    };