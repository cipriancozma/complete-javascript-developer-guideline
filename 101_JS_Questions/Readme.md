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
