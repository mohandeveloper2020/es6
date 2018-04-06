# ES5 vs ES6

```js
// Variable declaration
var x = 0;
let x = 0;

// Constant declaration
const X = 0;

// Arrow Functions
function x(y) {}
let x = y => {} // parentheses optional with one parameter

function x(a, b, c) {} 
let x = (a, b, c) => {}

// Template literals
var x = 'Release date: ' + date;
let x = `Release Date: ${date}`;

var x = 'This text ' +
        'is on ' +
        'multiple lines';

let x = `This text
         is on
         multiple lines`;        

// Implicit returns
function x(a, b, c) { return a + b + c; } 
let x = (a, b, c) => a + b + c;

// Key/property shorthand
var x = { a: a, b: b, c: 0 }
let x = { a, b, c: 0 }

// Object matching shorthand
var x = { a : 1, b : 2, c : 3 };

var a = x.a;
var b = x.b;
var c = x.c;

let {a, b, c} = x;

// for of (array)
var x = [1, 2, 3];

for (var i = 0; i < x.length; i++) {
    console.log(i);
}
for (let i of x) {
    console.log(i);
}

// default parameters
let x = (a, b = 2) => {
    console.log(a + b);
}
var x = function(a, b) {
    b = (b === undefined) ? 2 : b;
    console.log(a + b);
}
x(1);

// spread operator
let x = [1, 2, 3];
let y = ['a', 'b', 'c'];
let z = [...x, ...y];

console.log(z);



// modules
```
