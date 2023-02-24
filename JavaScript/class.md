> Class

- class안에는 속성(field), 행동(method)이 종합적으로 묶여있다.
- 객체지향언어
- **template**, 틀, 청사진 정의
- declare once 한번만 선언
- no data in
- ES6
- syntactical sugar over prototype-based inheritance: 기존에 존재하던 프로토타입 베이스에 기반해서 문법만 class 추가된 것.

1.  Class declarations

```
    class Person{
     // constructor
     constructor(name, age) {
     // fields
     this.name = name;
     this.age = age;
     }
        // methods
        speak(){
            console.log(`${this.name}: hello!`);
        }
    }
    const ellie = new Person('ellie', 20);
    ellie.speak(); //ellie: hello!
```

2. Getter and Setters

```
    class User{
        constructor(firstName, lastName, age){
            this. firstName = firstName;
            this.lastName = lastName;
            this.age = age;
        }

        get age(){
            return this._age;
        }

        set age(value){
            this._age = value<0 ? 0 : value;
        }
    }

    const user1 = new User('Steve','Job',-1)
    console.log(user1.age);
```

3. Fields (public, private)

- too soon!
- https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference

```
class Experiment {
    publicField = 2;
    #privateField = 0;
}
const experiement = new Experiment();
console.log(experiement.privateField);
```

4. Static properties and methods

- too soon!
- 오브젝트에 상관없이, 들어오는 데이터에 상관없이, 공통적으로 클래스에서 쓸 수 있는 거라면 static과 static 메소드를 이용해서 작성하는 것이 메모리 사용을 줄여 줄 수 있다.

```
class Article{
    static publisher = 'Dream Coding';
    constructor(articleNumber){
        this.articleNumber = articleNumber;
    }

    static printPublisher(){
        console.log(Article.publisher);
    }
}

console.log(Article.publisher);
Article.printPublisher();
```

5. Inheritance

- a way for one class to extend another class.
- 재사용

```
class Shape{
    constructor(width, height, color){
        this.width = width;
        this.height = height;
        this.color = color;
    }

    draw(){
        console.log(`drawing ${this.color} color!`)
    }

    getArea(){
        return this.width * this.height;
    }

    class Rectangle extends Shape {}
    class Triangle extends Shape {
        // 필요한 함수만 재정의해서 사용할 수 있다.

        draw(){
            // 부모 함수의 메소드 호출
            super.draw();
            // 새로 정의한 메소드
            console.log('😂')
        }
        getArea() {
            return (this.width * this.height) / 2
        }
    }

    const rectangle = new Rectangle(20, 20, 'blue');
    rectangle.draw();
    console.log(rectangle.getArea());

    const triangle = new Triangle(20, 20, 'red');
    triangle.draw();
    console.log(triangle.getArea());
}
```

6. Class checking: instanceOf 상속확인

```
console.log(rectangle instanceOf Rectangle); true
console.log(triangle instanceOf Rectangle); false
console.log(triangle instanceOf Triangle); true
console.log(triangle instanceOf Shape); true
console.log(triangle instanceOf Object); true

```
