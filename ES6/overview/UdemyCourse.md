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