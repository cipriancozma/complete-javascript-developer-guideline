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

    The splice method returns either the added/removed items from an array.

    let arrayInt1 = [1, 2, 3, 4, 5];
    let arrayInt2 = [1, 2, 3, 4, 5];
    let arrayInt3 = [1, 2, 3, 4, 5];

    let arr1 = arrayInt1.splice(0,2); // [1, 2]
    let arr2 = arrayInt2.splice(3); // [4, 5]
    let arr3 = arrayInt3.splice(3, 1, "a", "b", "c"); // returns [4];

    Splice method modifies the original array and returns the deleted array.

# 7. What is the difference between slice and splice?

    Slice ----------------------------------- Splice
    Doesn't modify the original array         Modifies the original array
    Returns the subset of orignal array       Returns the deleted elements as array
    Used to pick the elements from array      Used to insert/delete elements to/from array

# 8. How do you compare Object and Map?

    Objects are similar to Maps in that both let you set keys to values, retrieve those values, delete keys and detect whether something is stored at a key.

    Due to this reason, Objects have been used as Maps historically. But there are important differences that make using a Map preferable in certain cases.

    i. The keys of an Object are Strings and Symbols, whereas they can be any value for Map, including functions, objects and any primitive.
    ii. The keys in Map are ordered while keys added to Object are not. Thus, when iterating over it, a Map object returns keys in order of insertion.
    iii. You can get the size of a Map easily with the size property, while the number of properties in an Object must be determined manually
    iv. A Map is an iterable and can thus be directly iterated, whereas iterating over an Object requires obtaining its keys in some way and iterating over them
    v. A Map may perform better in scenarios involving frequent addition and removal of key pairs.

# 9. What is the difference between == and === operators?

    The === strict operators take type of variable in consideration, while == non-strict operators make type correction/conversion based upon values of variables.

    0 == false // true
    0 === false // false
    1 == "1" // true
    1 === "1" // false
    null == undefined // true
    null === undefined // false
    [] == [] or [] === [] or {} == {} or {} === {} // false, refer different objects in memory

# 10. What are lambda or arrow functions?

    An arrow function is a shorter syntax for a function expression and does not have its own this, arguments or super.

# 11. What is a first class function?

    In JavaScript, functions are first class objects. First class functions means when functions in that language are treated like any other variable.

    For instance, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable.

    const handler = () => console.log('This is a click handler function);
    document.addEventListener('click', handler);

# 12. What is a first order function?

    First order function is a function that doesn't accept another function as an argument and doesn't return a function as its return value.

    const firstOrder = () => console.log("I am a first order function");

# 13. What is a higher order function?

    Higher order function is a function that accepts another function as an argument or returns a function as a return value or both

    const firstOrderFunc = () => console.log("First Order Function");
    const higherOrder = firstOrderFunc => firstOrderFunc();
    higherOrder(firstOrderFunc);

# 14. What is a unary function?

    Unary function is a function that accepts exactly one argument. It stands for a single argument accepted by a function.

    const unaryFunction = a => console.log(a + 10);

# 15. What is the currying function?
