> Object

- **instance of a class** 클래스를 이용해 인스턴스를 만듦
- created many times
- data in
- 앙금 넣은 붕어빵
- 변수 하나당 값을 하나 넣을 수 있다.
- 나중에 프로퍼티를 추가하고 삭제할 수는 있지만 너무 동적으로 사용하면 유지보수에 좋지 않다.
- object = {key : value};

1. Literals and properties

```
const obj1 = {}; // 'object literal' syntax
const obj2 = new Object(); // 'object constructor' syntax

```

2. Computed properties 계산된 프로퍼티들

- key should be always string

```
console.log(ellie.name); // 코딩하는 그 순간 key에 해당하는 값을 받아오고 싶을 때
console.log(ellie['name']); // object 변수에 string 타입으로 접근이 가능하다.

ellie['hasJob'] = true; // 추가 가능
```

- 코딩하는 시점에 어떤 key가 필요한지 모를 때, 즉, 런타임에서 결정될 때
- 동적으로 실시간으로 value 값을 받아오고 싶을 때 사용

```
function printValue(obj, key){
    console.log(obj[key]);
}
printValue(ellie, 'name');
printValue(ellie, 'age');

```

3. Property value shorthand

- key와 value의 이름이 동일하다면 생략 가능. (name: name => name)

```
const person1 = { name: 'bob', age: 2 };
const person2 = { name: 'steve', age: 3 };
const person3 = { name: 'dave', age: 4 };
const person4 = new Person('ellie', 30); // class에서 object를 만드는 것처럼 new
console.log(person4)

4. Contructor function

// Object로 생성하는 함수명은 대문자로 시작.
function Person(name, age){
    // this = {};
    this.name = name;
    this.age = age;
    // return this;
}

```

5. in operator: property existence check (key in obj)

```
console.log('name' in ellie); true
console.log('age' in ellie); true
console.log('random' in ellie); false
console.log(ellie.random); undefined
```

6. for..in vs for..of

- for (key in obj) : 객체안의 키들이 하나씩 찍힘

```
console.clear();
for (key in ellie){
    console.log(key);
}
```

- for (value of iterable) : 배열안의 값들이 하나씩 찍힘

```
const array = [1, 2, 4, 5]
for (value of array){
    console.log(value);
}
```

7. Fun cloning

- Object.assign(dest, [obj1, obj2, obj3...])

```
const user = {name: 'ellie', age: '20'};
const user2 = user;
console.log(user);

// old way
const user3 = {};
for (key in user){
    user3[key] = user[key];
}
console.clear();
console.log(user3);

// Object.assign
const user4 = {};
Object.assign(user4, user);
// ==
const user4 = Object.assign({}, user);
console.log(user4);

// another example
const fruit1 = { color: 'red' };
const fruit2 = { color: 'blue', size: 'big' };
const mixed = Object.assign({}, fruit1, fruit2);
console.log(mixed.color); //blue
console.log(mixed.size); //big
// ===> 뒤에 프로퍼티로 덮임


```
