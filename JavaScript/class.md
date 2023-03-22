> Class

- class안에는 속성(field), 행동(method)이 종합적으로 묶여있다.
- Class는 객체를 생성하기 위한 템플릿. 클래스는 데이터와 이를 조작하는 코드를 하나로 추상화한다.
- 객체지향언어
- **template**, 틀, 청사진 정의
- declare once 한번만 선언
- no data in
- ES6
- syntactical sugar over prototype-based inheritance: 기존에 존재하던 프로토타입 베이스에 기반해서 문법만 class 추가된 것.
- 함수 선언과 클래스 선언의 중요한 차이점은 함수의 경우 정의하기 하기 전에 호출할 수 있지만, 클래스는 반드시 정의한 뒤에 사용할 수 있다는 점이다. 예외가 발생하는 이유는 클래스가 호이스팅될 때 초기화는 되지 않기 때문이다.
- 클래스의 본문(body)은 strict mode에서 실행됩니다.

- Constructor (생성자)
  - class 로 생성된 객체를 생성하고 초기화하기 위한 특수한 메서드
  - 클래스 안에 한 개만 존재
  - constructor는 부모 클래스의 constructor를 호출하기 위해 super 키워드를 사용할 수 있습니다.

1.  Defining classes : Declarations

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

2. Defining classes : Expression

- Class 표현식은 이름을 가질 수도 있고, 갖지 않을 수도 있다. 이름을 가진 class 표현식의 이름은 클래스 body의 local scope에 한해 유효하다. (하지만, 클래스의 (인스턴스 이름이 아닌) name 속성을 통해 찾을 수 있다).

```
    // unnamed
    let Rectangle = class {
    constructor(height, width) {
        this.height = height;
        this.width = width;
    }
    };
    console.log(Rectangle.name);
    // 출력: "Rectangle"

    // named
    let Rectangle = class Rectangle2 {
    constructor(height, width) {
        this.height = height;
        this.width = width;
    }
    };
    console.log(Rectangle.name);
    // 출력: "Rectangle2"
```

3. Getter and Setters

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

- static 키워드는 클래스를 위한 정적(static) 메서드를 정의한다. 정적 메서드는 클래스의 인스턴스화(instantiating) 없이 호출되며, 클래스의 인스턴스에서는 호출할 수 없다.
- 정적 메서드는 어플리케이션(application)을 위한 유틸리티(utility) 함수를 생성하는 데 주로 사용된다. 반면, 정적 속성은 캐시, 고정 환경설정 또는 인스턴스 간에 복제할 필요가 없는 기타 데이터에 유용하다.
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
- extends 키워드는 클래스 선언이나 클래스 표현식에서 다른 클래스의 자식 클래스를 생성하기 위해 사용된다.
- subclass에 constructor가 있다면, "this"를 사용하기 전에 가장 먼저 super()를 호출해야 한다.
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
