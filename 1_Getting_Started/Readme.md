# 01. What is JavaScript

JavaScript is a programming language designed to interact with elements of web pages.
In web browsers, JavaScript consists of three main parts:

- ECMAScript that provides the core functionality
- The Document Object Model (DOM) which provides interfaces for interacting with elements on web pages
- The Browser Object Model (BOM) which provides API for interacting with web browsers.

JavaScript allows you to add interactivity to a web page. It is often used with HTML and CSS to enhance to functionality of a web page such as validating forms, creating interactive maps and displaying animated charts.

When a web page is loaded i.e. after HTML and CSS have been downloaded, the JS engine in the web browser executes the JS code.
The JS code then modifies the HTML and CSS to dynamically update the user interface.

The JS engine is a program that executes JS code. In the beginning, JS engines were implemented as interpreters.
However, modern JS engines are typically implemented as just-in-time compilers that compile JS code to bytecode for improved performance.

## Client-side vs Server-side JavaScript

When JS is used on a web page, it is executed in the web browsers of user's computers. In this case JS works as a client-side language.

JS can run on both web browsers and servers. A popular server-side environment for JS is Node.js. Unlike the client-side JS, the server-side JS executes on the server that allows you to access databases, file systems, etc.

## JavaScript History

1995 -> JS was created by a Netscape developer named Brendan Eich.
1997 -> JS is starting to be standardized and a new standard defines a new scripting language named ECMAScript. The International Organization for Standardization and International Electrotechnical Commisions adopted ECMAScript as a standard.

## Overview of JavaScript

To define a variable in JS, you use var keyword. For instance:

    var x = 10;
    var y = 20;

ES6 added a new way to declare a variable with the let keyword:

    let x = 10;
    let y = 20;

To declare a function you use the function keyword. The following example defines a function that calculates the sum of two arguments:

    function add(a, b) {
        return a + b;
    }

To call the add() function you use the following syntax:

    let result = add(x, y);

To log the result into the console window of the web browser, you use the console.log():

    console.log(result);

Now you should see 30 in the console window.

JS provides you with the condition statements such as if-else and switch statements. For instance:
