# Udemy Course - Essentials in JavaScript ES6 - A Fun and Clear Introduction
#### Author: David Katz (http://davidtkatz.com)
#### Platform: Online Course
---

* [Introduction](#introduction)
* [But why Babel?](#but-why-babel)
* [Alright, so Why webpack?](#alright-so-why-webpack)
* [Variables and Scope in ES6](#variables-and-scope-in-es6)
    * [LET there be variables](#let-there-be-variables)
    * [CONST is key](#const-is-key)
* [Template Literals](#template-literals)
* [The Spread operator](#the-spread-operator)
* [Destructuring Assignments](#destructuring-assignments)
* [Arrow functions](#arrow-functions)
    * [Exporting values](#exporting-values)
* [Object Oriented Programming on ES6](#object-oriented-programming-on-es6)

## Introduction

ES6 is the sixth standard of the JavaScript language, which will be compiled (for the moment), using Babel, Webpack.

## But why Babel?

You'll need a transpiler to use ES6, because older browsers won't run new ES6 code.
With Babel, you'll be able to transpile ES6 to pre-ES6 code.

## Alright, so Why webpack?

Webpack is awesome when it comes to bundle all your .js files into one single file.
Also, it comes with a dev-server, which reloads everything for you (no more "alt-tab F5").

## Variables and Scope in ES6

### LET there be variables

The ``var`` keyword used to rule on JavaScript. Now, you have a ``let`` keyword.
You may use curly braces to scope variables declared with ``let``.
An example would be:

```javascript
let myvar = 'Hi';

{
    let myvar = 'Hello';
}
```
The variable inside the curly braces is actually a different variable. The curly braces define a different scope on ES6.
If you declare a variable inside a block scope, you won't be able to access it from outside, as in:

```javascript
{
    let myvar = 'Hello';
}
console.log(myvar) //Error: There is no 'myvar'.
```

### CONST is key

The ``const`` keyword consists of a constant.
Constants don't lock the value of the variable, but the assignment of the variable. You may be able, for instance, to add items to an array created with ``const``, for example. It gives you protection, so the variables will remain teh same.

## Template Literals

You can concatenate strings with a new fashion! Instead of:

```javascript
var a = 'Foo';
var b = 'Bar';
var c = a + ' ' + b;
console.log(c); // Outputs: Foo Bar
```

You can simply:

```javascript
let a = 'Foo';
let b = `${a} Bar`;
console.log(b); // Outputs: Foo Bra
```

## The Spread operator

A wonderful tool to deal with arrays.
It's a ``...``, but it's more than it's looks.
As an example:

```javascript
function arrayprinter(...a){
    console.log(a);
}

arrayprinter(1,2,3,4); // Outputs: [1,2,3,4]
```

## Destructuring Assignments

Instead of doing something like:

```javascript
var myArray = [100,200];
var value1  = myArray[0];
var value2  = myArray[1];

console.log(value1, value2); // Outputs: 100 200

```

You can do:

```javascript
let myArray          = [100,200];
let [value1, value2] = c;
console.log(value1, value2); // Outputs: 100 200

```

They variables inside the second array will get the values from the first by their position.

You can use it with the spread operator, as in:

```javascript
let myArray                  = [100,200,300,400,500];
let [value1, ...otherValues] = myArray;
console.log(value1, otherValues); // Outputs: 100, [200,300,400,500]

```

You can use Destructuring Assignments with objects as well, as, for example, make this bit of code:

```javascript
var car   = {color: "red", year: 2017};
var color =  car.color;
var year  =  car.year;
console.log(color, year); // Outputs: red 2017

```

Like this:

```javascript
let car           = {color: "red", year: 2017};
let {color, year} = car;

console.log(color, year); // Outputs: red 2017

```

And it'll work. It matches the keys and values by position on our object.

## Arrow functions

Arrow functions consists of Anonymous functions, declared with and operator instead of a function name.

An example:

```javascript
pomodoro(function(){
    console.log("Time to stop"); // Outputs: Time to stop
}, 1000);
```

Can be written as:

```javascript
pomodoro(() => {
    console.log("Time to stop"); // Outputs: Time to stop
});
```

Functions have their own scope, they bind to their **own** this, arrow functions **don't** bind to their own this, using the parent instead.
An example:

```javascript
this.a = 2;

let print  = function() {
    this.a = 5;
    console.log(this.a); // Outputs: 5
}

let arrowPrint = () => {
    console.log(this.a); // Outputs: 2
}

```

The map function allows us to create arrays by calling a function on each element of the array, and thus is a great example of ES6 usage of arrow functions.

```javascript
let myArray = [10,20,30];

let addOne  = function(element) {
    return element + 1;
}

myArray = myArray.map(addOne);

console.log(myArray); // Outputs: [11, 21, 31]

```

Filter is another helper method that is widely used on ES6.
It's quite popular and takes advantage of arrow  functions. 
It returns a new array based on an existing array, but instead of returning an array of the same size, it returns an array based on some criteria. For example:

```javascript
let isPassing = (grade) => {
    return grade >= 70;
}

let scores  = [90,85,67,71,70,55,92];
let passing = scores.filter(isPassing);

console.log(passing); // Outputs: [90,85,71,70,92]
```

It can be written like:

```javascript
let scores  = [90,85,67,71,70,55,92];
let passing = scores.filter(element => element >= 70);

console.log(passing); // Outputs: [90,85,71,70,92]

```
There are more helper methods beside `map` and `filter`, like:

```javascript

find();    // Returns a value in an array that passes a given test
forEach(); // Similar to map, calls a function on each array element.
```

> Arrow functions work like normal method expressions in JavaScript, but with a shorter syntax. They also have the added benefit of being anonymous. In addition, unlike normal JavaScript function, they do not bind the this object to their function scope.
The map helper method in es6 allows us to create arrays by calling a function on each element of an initial array.
The filter helper method in es6 creates new arrays with all the same elements of an initial array depending on a test that we give it (David Katz).

### Exporting values

Modules helps us to separate code, avoiding the creation of a single monolithic file, for example.

You may export classes and variables, for example, using the `export` keyword before the declaration, like so:

```javascript
const test = () => {
    return true;
}

export {test};

```

You may access the exported data by using the `import`keyword followed by a name and a path, as in:

```javascript
import {package} from './path';

```
You may also imply an default export, like:

```javascript
const foo = () => {
  return true;
}

const bar = () => {
  return false;
}

export { foo, bar }
export defaul foo;

```

## Object Oriented Programming on ES6

ES6 includes classes, making it easier to write OOP software using JavaScript.

To create classes, use the `class` keyword. The default class would look like:

```javascript
class Parent {
    constructor(name, height){
        this.name   = name;
        this.height = height;
    }
    
    greet() {
        console.log(`Hi, my name is ${this.name}`);
    }
}


```

You can create an instance of that class by doing:

```javascript
let Test = new Parent("Test", 180);
Test.greet(); // Outputs: Hi, my name is Test
```

You can use the `extends` keyword to extend classes, as in other oop programming languages. The `super` keyword is used to access the parent-class attributes. 

