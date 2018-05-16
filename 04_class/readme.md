# class

## class

기존 객체지향 구현은 function 을 생성자로 사용해 복잡해진 코드. class키워드로 객체지향 프로그래밍.

    class Lang {
        constructor(name){
            this.name = name;
        }
        getName(){
            return this.name;
        }
    }
    let lang = new Lang("Language");
    console.log("Lang,getName();" + lang.getName());
    
    // 실행결과 
    lang.getNmae();Language
    
## class 상속

다른 객체지향 언어들처럼 extends 키워드로 사용해 상속.

상속은 부모 클래스에 정의된 메서드나 변수를 자식 클래스에서 사용할 수 있게 해줌

    class Lang {
       constructor(name){
            this.name = name;
       }
       getName(){
             return this.name;
       }
    }
    let lang = new Lang("Language");
    console.log("Lang,getName();" + lang.getName());

    class JavaScript extends Lang{
        constructor(name){
            super(name);
        }
    }
    let js = new JavaScript("JavaScript");
    console.log("js instanceof JavaScript : " + (js instanceof JavaScript));
    console.log("js instanceof Lang : " + (js instanceof Lang));
    console.log("js.getName(): " + js.getName());
    
    // 실행결과
    lang.getNmae();Language
    js instanceof JavaScript : true
    js instandeof Lang: true
    js.getName(): JavaScript
    
## 정리하기

class 내부적으로 함수처럼 동작.

클래스와 상속으로 객체지향 프로그래밍 가능.