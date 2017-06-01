# es6-course

Welcome to the es6-course wiki!

https://egghead.io/courses/learn-es6-ecmascript-2015

## let keyword

- Allow you use block scopping.
- Avoid hoisting mistakes.

```javascript
 let name = 'peter';
```

**ES5**
```javascript
var message = 'hi';
for(var i = 0; i < 3, i++){
    var message = 'bye';
}
console.log(message);
// bye
```

-----------------------

**ES6**
```javascript
let message = 'hi';
for(var i = 0; i < 3, i++){
    let message = 'bye';
}
console.log(message);
// hi
```

## Default Values for Function Parameters

Syntax

```javascript
function test([param1[ = defaultValue1 ]) {
   // statements
}
```

**ES6**

```javascript
function greet(greeting, name = 'Peter'){
 console.log(greeting + ': ' + name);
}

greet('Hello');
// hello, Peter

greet('Hello', 'Hugo');
// hello: Hugo
```

## const Declarations

Read only variables.

Syntax

```javascript
const PATH = 'home/dariel'
```

**ES5**

```javascript
var PATH = 'home/dariel';
PATH = 'usr/local';

console.log(PATH);
// 'usr/local'
```

**ES6**

```javascript
const PATH = 'home/dariel';
PATH = 'usr/local';

// Uncaught TypeError: Assignment to constant variable.(…)
```

## Shorthand Properties

Compose complex objects from other objects.

**ES5**

```javascript

let name = 'Rene';
let age = 34;

let person = {name, age};

console.log(person);
// {name: 'Rene', age: 34}
```

## Spread operator

Allows you to "explode" an array into its individual elements.

**ES6**
```javascript

let numbers = [1, 2, 3];

console.log(...numbers);
// 1,2,3
```
Can also be used in function parameters

**ES6**
```javascript

let numbers = [1, 2, 3];

function sum(a, b, c){
  return a + b + c;
}

sum(...numbers);
// 6
```

## String Templates

**ES5**
```javascript

let salutation = "Hello";
let greeting = salutation + ", World"

console.log(greeting);
// Hello, World
```
----------------------------

**ES6**
```javascript

let salutation = "Hello";
let greeting = `${salutation}, World`

console.log(greeting);
// Hello, World
```
> note: Respect the whitespaces, line breaks, etc;

**You can also do expressions ;)**

**ES6**
```javascript

let x =3;
let y = 4;
let equation = `${x} + ${y} = ${x + y}`;

console.log(equation);
// 3 + 4 = 7
```

**Tagged template literals**

You are able to modify the output of template literals using a function.

**ES6**

```javascript
var a = 5;
var b = 10;

function tag(strings, ...values) {
  console.log(strings[0]); // "Hello "
  console.log(strings[1]); // " world "
  return "Bazinga!";
}

tag`Hello ${ a + b } world ${ a * b }`;
// "Bazinga!"
```
## Destructuring Assignment

Provides flexible options for variable assignment.

**ES5**

```javascript
var obj = {
 color: "blue"
}

console.log(obj.color);
// blue
```

**ES6**

```javascript

// lookup the 'color' property and make it available

var {color} = {
 color: "blue"
}

console.log(color);
// blue
```

**Multiple properties**

**ES6**

```javascript
var {color, position} = {
 color: "blue",
 position: '30px',
 tag: 'span'
}

console.log(color);
// blue
console.log(position);
// 30px
```

**Using different names**

**ES6**

```javascript
var {color: primaryColor, position: globalPosition} = {
 color: "blue",
 position: '30px',
 tag: 'span'
}

console.log(primaryColor);
// blue
console.log(globalPosition);
// 30px
```

## Import and Export

This **inserts myModule** into the **current scope**, containing **all the exported bindings** from "my-module.js".**

```javascript

import * as myModule from "my-module";

```

Import a **single member of a module**. This inserts myMember into the **current scope**.

```javascript

import {myMember} from "my-module";

```

Import **multiple members** of a module. This inserts both foo and bar into the **current scope**.

```javascript

import {foo, bar} from "my-module";

```

Import **a member** with a more **convenient alias**. This inserts shortName into the current scope.

```javascript

import {reallyReallyLongModuleMemberName as shortName} from "my-module";

```

Import **multiple members** of a module with **convenient aliases**.

```javascript

import {reallyReallyLongModuleMemberName as shortName, anotherLongModuleName as short} from "my-module";

```

Import an **entire module** for side effects only, **without importing any bindings**.

```javascript

import "my-module";

```

## Array.from()

Array.from() lets you convert an "iterable" object (AKA an array-like object) to an array.

```javascript

const akaObject = 
   Array.from()document.querySelectorAll('.deals');

```

## Promises with ES6

```javascript
var d = new Promise((resolve, reject) => {
  if (true) {
   resolve('hello world');
  } else {
   reject('no bueno');
  }
});

d.then((data) => console.log('success: ' + data));
d.catch((error) => console.log('error: ' + error));
```

**If you don't want to use the catch method**

```javascript

d.then(
  (data) => console.log('success: ' + data),
  (error) => console.log('error: ' + error)
);

```

**You can call multiple functions**

```javascript
d
 .then((data) => {
   console.log('success: ' + data));
   return 'passing data to the other function'; 
 }
 .then((data) => console.log('data from the previous then: ' + data));
```

## Maps and WeakMaps

Map is a key/value data structure in ES6. It provides a better data structure to be used for hash-maps. 
Here’s how what we had earlier looks like with ES6 maps.

**API**

- set()
- get()
- size()
- clear()
- has()

```javascript

var myMap = new Map();
myMap.set('foo', 'bar');
myMap.set('test', 'aaa');

myMap.get('qwerty');

```
