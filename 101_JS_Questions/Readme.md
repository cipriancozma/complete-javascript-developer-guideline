# 1. What are the possible ways to create objects in JS?

i. Object Constructor
Currently this approach is not recommended.

    let object = new Object();

ii. Object create method

    let object = Object.create(null);

iii. Object literal syntax

    let object = {};

iv. Function constructor

    function Person(name) {
    let object = {};

    object.name = name;
    object.age = 21;
    return object;

    }

    let newObj = new Person("Ciprian");

v. Function constructor with prototype

    function Person() {}
    Person.prototype.name = 'Ciprian';
    let objectObj = new Person();

vi. ES6 Class syntax

    class Person() {
        constructor(name) {
            this.name = name;
        }
    }

    let object = new Person("Cozma");

vii. Singleton pattern
A Singleton is an object which can be instantiated only one time.
Repeated calls to its constructor return the same instance and this way one can ensure that they don't accidentally create multiple instances.

    let object = new function(){
        this.name = "Ciprian";
    }

# 2. What is a prototype chain?

Prototype chaining is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.
The prototype on object instance is available through Object.getPrototypeOf(object) or proto property.

# 3. What is the difference between Call, Apply and Bind?

Call: The call() method invokes a function with a given this value and arguments provided one by one

    let employee1 = { firstName: 'John', lastName: 'Rodson' };
    let employee2 = { firstName: 'Jimmy', lastName: 'Baily' };

    function invite(greeting1, greeting2) {
        console.log(greeting1 + ' ' +  this.firstName + ' ' + this.lastName + ' ' + greeting2);
    }

    invite.call(employee1, 'Hello', 'How are you?'); // Hello John Rodson, How are you?
    invite.call(employee2, 'Hello', 'How are you?'); // Hello Jimmy Baily, How are you?

Apply: Invokes the function with a given this and allows you to pass the arguments as an array

    let employee1 = { firstName: 'John', lastName: 'Rodson' };
    let employee2 = { firstName: 'Jimmy', lastName: 'Baily' };

    function invite(greeting1, greeting2) {
        console.log(greeting1 + ' ' +  this.firstName + ' ' + this.lastName + ' ' + greeting2);
    }

    invite.apply(employee1, ['Hello', 'How are you?']); // Hello John Rodson, How are you?
    invite.apply(employee2, ['Hello', 'How are you?']); // Hello Jimmy Baily, How are you?

Bind: returns a new function allowing you to pass any number of arguments

    let employee1 = { firstName: 'John', lastName: 'Rodson' };
    let employee2 = { firstName: 'Jimmy', lastName: 'Baily' };

    function invite(greeting1, greeting2) {
        console.log(greeting1 + ' ' +  this.firstName + ' ' + this.lastName + ' ' + greeting2);
    }

    let inviteEmployee1 = invite.bind(employee1);
    let inviteEmployee2 = invite.bind(employee2);


    inviteEmployee1('Hello', 'How are you?'); // Hello John Rodson, How are you?
    inviteEmployee2('Hello', 'How are you?'); // Hello Jimmy Baily, How are you?

Call and Apply can be used interchangeable, but bind is different, it creates a new function that will have this set to the first parameter passed to bind().

# 4. What is JSON and its common operations?

JSON is useful when you want to transmit data across a network and it is basically just a text file with an extension of .json

To convert a string to a native object

    JSON.parse(text)

To convert a native object to a string

    JSON.stringify(text)

# 5. What is the purpose of the array slice method?

    The slice method returns the selected elements in an array as a new array object.

    let arrayInt = [1, 2, 3, 4, 5];
    let arrayInt1 = arrayInt.slice(0, 2); // returns [1, 2]
    let arrayInt2 = arrayInt.slice(2, 3); // returns [3]
    let arrayInt3 = arrayInt.slice(4); // returns [5];

# 6. What is the purpose of the array splice method?
