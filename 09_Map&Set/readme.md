# Map

Map은 key와 value가 한쌍인 컬렉

    const myMap = new Map();
    myMap.set("Lang","JavaScript");
    
    const myData = new Map([
        ["key1","value1"],
        ["key2","value2"]
    ]);
    console.log(myData.get("key1"));
    
    // 실행결과
    value1
    
초기화하면서 배열로 값을 할당할 수 있으며 get 메서드에 key 를 사용해서 value 를 출력할 수 있음

    
Map 예제2

    const myMap = new Map();
    // myMap.set("Plugin","Update").set("Refactor",6).set("Code",5);
    const myArray = [["Plugin","Update"],["Refactor",6], ["Code",5]];
    
    for(let i of myArray){
        myMap.set(...i);
    }
    myMap.delete("Hello");
    for(let [key, value] of myMap){
        console.log(key + "," + value)
    }
    
    // 실행결과
    Plugin,Update
    Refactor,6
    Code,5
    
set메서드를 연속해서 데이터를 할당 할 수 도 있음

delete메서드에 key를 넣어 삭제할 수 있음.