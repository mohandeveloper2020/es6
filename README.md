# ES5 vs ES6 Syntax

Quick reference

> **Note:** I'll be using `let` in place of `var` for all ES6 examples.

### `var`, `let`, `const`

| Keyword                                                                                       | Scope          | Hoisting | Can Be Reassigned | Can Be Redeclared |
| --------------------------------------------------------------------------------------------- | -------------- | -------- | ----------------- | ----------------- |
| [`var`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)     | Function scope | Yes      | Yes               | Yes               |
| [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)     | Block scope    | No       | Yes               | No                |
| [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) | Block scope    | No       | No                | No                |

### Variable declaration

```js
// ES5
var x = 0;
```

```js
// ES6 
let x = 0;
```


### Constant declaration

```js
// ES6
const X = 0; // constants are uppercase by convention
```

### Arrow functions

```js
// ES5
function x(y) {}        // function declaration
var x = function(y) {}  // function expression
```

```js
// ES6
let x = y => {}         // parentheses optional with one parameter
let x = (a, b, c) => {} // parentheses required with multiple parameters
```

### Template literals

#### Concatenation/string interpolation

```js
// ES5
var x = 'Release date: ' + date;
```

```js
// ES6
let x = `Release Date: ${date}`;
```

#### Multi-line strings

```js
// ES5
var x = 'This text ' +
        'is on ' +
        'multiple lines';
```

```js
// ES6
let x = `This text
         is on
         multiple lines`;        
```

### Implicit returns

```js
// ES5
function x(a, b, c) { return a + b + c; } 
```

```js
// ES6
let x = (a, b, c) => a + b + c; // curly brackets must be omitted
```


### Key/property shorthand

```js
// ES5
var x = { 
    a: a, 
    b: b, 
    c: 0 
}
```

```js
// ES6
let x = { 
    a, 
    b, 
    c: 0 
}
```

### Method properties shorthand

```js
// ES5
var x = {
    a: function(c, d) {},
    b: function(e, f) {}
};
```

```js
// ES6
let x = {
    a(c, d) {},
    b(e, f) {}
}
```

### Object matching shorthand

```js
var x = { a: 1, b: 2, c: 3 };
```

```js
// ES5
var a = x.a;
var b = x.b;
var c = x.c;
```

```js
// ES6
let {a, b, c} = x;
```

### Looping through an array

```js
var x = [1, 2, 3];
```

```js
// ES5
for (var i = 0; i < x.length; i++) {
    console.log(i);
}
```

```js
// ES6
for (let i of x) {
    console.log(i);
}
```

### Default parameters

```js
// ES5
var x = function(a, b) {
    b = (b === undefined) ? 2 : b;
    return a + b;
}
```

```js
// ES6
let x = (a, b = 2) => {
    return a + b;
}
```

```js
x(10);   // returns 12
x(10, 5) // returns 15
```

### Spread operator

```js
let x = [1, 2, 3];
let y = ['a', 'b', 'c'];
let z = [...x, ...y];
```

console.log(z);

// Classes
function X(a, b) {
    this.a = a;
    this.b = b;
}

X.prototype.d = function () {
    console.log(this.a + this.b);
}

var x = new X(1, 2);
x.d();

class X {
    constructor(a, b) {
        this.a = a;
        this.b = a;
    }

    d() {
        console.log(this.a + this.b);
    }
}

const x = new X(1, 2);
x.d();

// Inheritance
function Y(a, b, c) {
    X.call(this, a, b);

    this.c = c;
}

Y.prototype = Object.create(X.prototype);
Y.prototype.z = function () {
    console.log(this.a + this.b + this.c);
}
var y = new Y(1, 2, 3);
y.z();

class Y extends X {
    constructor(a, b, c) {
        super(a, b);

        this.c = c;
    }

    z() {
        console.log(this.a + this.b + this.c);
    }
}
const y = new Y(1, 2, 3);
y.z();

// modules
//<script src="export.js"></script>
//<script type="module" src="import.js"></script>

// export.js
let x = y => y + y;
let z = 0;

export { x, z };

// import.js
import { x, z } from './export.js';
console.log(x(3), z);
