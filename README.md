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
const X = 0;
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
var x = {
    a: function(c, d) {},
    b: function(e, f) {}
};

let x = {
    a(c, d) {},
    b(e, f) {}
}

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
