# 나머지 매개 변수 rest parameter

가변 인자에 대한 기능을 추가

"__" 키워드가 추가

함수를 선언할때 매개변수에 사용.

    function myFunction(a,b,c,d,...rest){
        console.log(a,b);
        console.log(rest);
        console.log(rest.length);
    }
    myFunction(1,2,3,4,5,6,7,8)
    
    //  실행결과
    1 2
    [ 5, 6, 7, 8 ]
    4
    
# 전개 연산자 spread operator

함수를 호출할때 인자에 사용
    
    function rest(a,b,c, ...rest){
        console.log(b, c);
        
        for(let i of rest){
            console.log(i);
        }
    }
    
    var spread = [2, 3]
    
    rest(1, ...spread, 4, ...[5, 6]);
    
    //  실행결과
    2 3
    4
    5
    6
    
# 정리하기

나머지 매개변수는 2개 이상의 요소를 하나의 요소로 모이는 것

전개 연산자는 배열이나 객체를 확장