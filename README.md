# ES5 vs ES6

```js
// Variable declaration
var x = 0; // ES5
let x = 0; // ES6

// Constant declaration
const X = 0; // ES6

// Arrow Functions
function x(y) {} // ES5
let x = y => {}  // ES6

function x(a, b, c) {}  // ES5
let x = (a, b, c) => {} // ES6

// Template literals
var x = 'Release date: ' + date; // ES5
let x = `Release Date: ${date}`; // ES6

// ES5
var x = 'This text ' +
        'is on ' +
        'multiple lines';

// ES6
let x = `This text
         is on
         multiple lines`;        

// Implicit returns
function x(a, b, c) { return a + b + c; } // ES5 
let x = (a, b, c) => a + b + c;           // ES6  

// Key/property shorthand
var x = { a: a, b: b, c: 0 }
let x = { a, b, c: 0 }

// Object matching shorthand
var x = { a : 1, b : 2, c : 3 };

var a = x.a;
var b = x.b;
var c = x.c;

let {a, b, c} = x;

// Iterate through array
var x = [1, 2, 3];

for (var i = 0; i < x.length; i++) {
    console.log(i);
}
for (let i of x) {
    console.log(i);
}

// Default parameters
let x = (a, b = 2) => {
    console.log(a + b);
}
var x = function(a, b) {
    b = (b === undefined) ? 2 : b;
    console.log(a + b);
}
x(1);

// Spread operator
let x = [1, 2, 3];
let y = ['a', 'b', 'c'];
let z = [...x, ...y];

console.log(z);



// modules
```
