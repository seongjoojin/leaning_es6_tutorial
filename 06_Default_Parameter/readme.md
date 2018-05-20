# 기본 매개변수 (Default Parameter)

함수의 매개변수는 기본값이 undefined.

인자가 넘어오지 않을때의 기본값 설정.

    function animal(name){
        var name = name || "dog";
        console.log(name);
    }
    animal();
    animal(null);
    animal(false);
    
    //  실행결과
    dog
    dog
    dog
    
ES6는 인자가 넘어오지 않을때의 값을 설정할 수 있음

    const defaultColor = "red";
    function defaultValue(value, color = defaultColor, myArray = []){
        myArray.push(value, color);
        return console.log(myArray);
    }
    defaultValue("strawberry");
    defaultValue("apple",undefined);
    defaultValue("banana","yellow");
    
    //  실행결과
    
    ['strawberry', 'red']
    ['apple', 'red']
    ['banana', 'yellow']
    
주의해야할 점 : ES5까지의 방법은 undefined, null, false, 0, 공백에 대해 적용가능하나 ES6의 기본 매개변수는 undefined 일 경우에만 적용됨.

# 정리하기

인자가 undefined 로 돌아올 때 기본 매개변수를 사용