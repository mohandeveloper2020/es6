# ES5 vs ES6 Syntax

## Quick reference

> **Note:** I'll be using `let` in place of `var` for all ES6 examples.

## Key

- Object: `obj`
- Array: `arr`
- Function: `func`
- Parameter, method: `a`, `b`, `c`
- Variable: `x`
- String: `str`

### Variables and constants

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
const CONST_IDENTIFIER = 0; // constants are uppercase by convention
```

### Arrow functions

```js
// ES5
function func(a, b, c) {}        // function declaration
var func = function(a, b, c) {}  // function expression
```

```js
// ES6
let func = a => {}         // parentheses optional with one parameter
let func = (a, b, c) => {} // parentheses required with multiple parameters
```

### Template literals

#### Concatenation/string interpolation

```js
// ES5
var str = 'Release date: ' + date;
```

```js
// ES6
let str = `Release Date: ${date}`;
```

#### Multi-line strings

```js
// ES5
var str = 'This text ' +
        'is on ' +
        'multiple lines';
```

```js
// ES6
let str = `This text
         is on
         multiple lines`;        
```

### Implicit returns

```js
// ES5
function func(a, b, c) { return a + b + c; } 
```

```js
// ES6
let func = (a, b, c) => a + b + c; // curly brackets must be omitted
```


### Key/property shorthand

```js
// ES5
var obj = { 
    a: a, 
    b: b, 
    c: 0 
}
```

```js
// ES6
let obj = { 
    a, 
    b, 
    c: 0 
}
```

### Method properties shorthand

```js
// ES5
var obj = {
    a: function(c, d) {},
    b: function(e, f) {}
};
```

```js
// ES6
let obj = {
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
var a = obj.a;
var b = obj.b;
var c = obj.c;
```

```js
// ES6
let {a, b, c} = obj;
```

### Looping through an array

```js
var arr = [1, 2, 3];
```

```js
// ES5
for (var i = 0; i < arr.length; i++) {
    console.log(i);
}
```

```js
// ES6
for (let i of arr) {
    console.log(i);
}
```

### Default parameters

```js
// ES5
var func = function(a, b) {
    b = (b === undefined) ? 2 : b;
    return a + b;
}
```

```js
// ES6
let func = (a, b = 2) => {
    return a + b;
}
```

```js
func(10);   // returns 12
func(10, 5) // returns 15
```

### Spread operator

```js
// ES6
let arr1 = [1, 2, 3];
let arr2 = ['a', 'b', 'c'];
let arr3 = [...arr1, ...arr2];

console.log(arr3); // [1, 2, 3, "a", "b", "c"]
```

### Classes/constructor functions

```js
// ES5
function ExampleConstructor(a, b) {
    this.a = a;
    this.b = b;
}

ExampleConstructor.prototype.sum = function () {
    return this.a + this.b;
}

var example1 = new ExampleConstructor(3, 4);

example1.sum(); // returns 7
```

```js
// ES6
class ExampleClass {
    constructor(a, b) {
        this.a = a;
        this.b = b;
    }

    sum() {
        return this.a + this.b;
    }
}

let example1 = new ExampleClass(3, 4);

example1.sum(); // returns 7
```

### Inheritance

```js
// ES5
function Inheritance(a, b, c) {
    ExampleConstructor.call(this, a, b);

    this.c = c;
}

Inheritance.prototype = Object.create(ExampleConstructor.prototype);
Inheritance.prototype.product = function () {
    return this.a * this.b * this.c;
}

var example2 = new Inheritance(3, 4, 5);
example2.product(); // 60
```

```js
// ES6
class Inheritance extends ExampleClass {
    constructor(a, b, c) {
        super(a, b);

        this.c = c;
    }

    product() {
        return this.a * this.b * this.c;
    }
}

const example2 = new Inheritance(3, 4, 5);
example.product(); // 60
```

### Modules 

```html
<script src="export.js"></script>
<script type="module" src="import.js"></script>
```

```js
// export.js
let func = a => a + a;
let obj = {};
let x = 0;

export { func, obj, x };
```

```js
// import.js
import { func, obj, x } from './export.js';
console.log(func(3), obj, x);
```
