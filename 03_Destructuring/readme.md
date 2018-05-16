# Destructuring

## 비구조화 할당(destructuring assignment)

- 구조화된 object나 array를 비구조화 하여 변수에 할당

객체 또는 배열에서 데이터를 분석하 각각의 변수에 할당하는 것을 의미함.

    let data = [{
        count: 1,
        list: [{
            name: ["jack","paul"],
            group: "sports"
        }]
    }];
    
    let [{count, list: [{name, group}]}] = data;
    console.log(`
       count: ${count}
       group: ${group}
    `);
    
    //실행결과
    count: 1
    group: sports
    
예제2

    function productObject({name, price, color}){
        return {
            productName: "This product name: " + name,
            addToCart(){
                console.log(name + "is added");
            },
            detailView(){
                console.log(`
                    ${productName}
                    price: ${price}
                    color: ${color}
                `);
            }
        }
    }
    var {productName, addToCart, detailView} = productObject({name:"apple", price: 199, color: "silver"});
    addToCart();
    detailView();
    
    // 실행결과
    This product name: apple
    price: 199
    color: silver
    
## 정리하기

- 객체 또는 배열에서 데이터를 분석하여 각각의 변수에 할당