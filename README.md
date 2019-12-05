# JavaScript Study Guide
- [The Basics](#the-basics)
  * [Features of ES6](#features-of-es6)
  * [Data Types](#data-types)
  * [Loosely vs. Strictly Equal](#loosely-vs-strictly-equal)
- [Context and Scope](#context-and-scope)
  * [Context](#context)
  * [Scope](#scope)
  * [`this` keyword and context](#this-keyword-and-context)
  * [Currying](#currying)
- [Event Loop](#event-loop)
  * [Overview](#overview)
  * [Promises vs. Async/Await](#promises-vs-asyncawait)
- [Garbage Collection](#garbage-collection)
- [`eventListeners`](#eventlisteners)
- [The Different Engines](#the-different-engines)
# NERD Study Guide
- [React](#react)
  * [Architecture](#architecture)
  * [Virtual DOM](#virtual-dom)
- [Redux](#redux)
- [HTML](#html)
- [CSS](#css)
- [Express](#express)
- [SQL](#sql)

****

# JavaScript Study Guide

## Variable Declaration
 * `var`: Before ES6, it was the only variable. Scoped to global scope (everything can access it) or function scoped (only accessible within the function)
 * `let`: declares a new variable that be reassigned later on (note: possible with `var`)
 * `const`: declares new variable that cannot be reassigned (note: reassigning will throw an 'Uncaught TypeError'); default variable unless reassignment is necessary
 
## Data Types

### Primitive Data Types

#### What are primitive data types?
* A primitive is a data that is not an object and has no methods. 
* JS has 7 primitive data types: `string`, `number`, `bigint`, `boolean`, `null`, `undefined`, and `symbol` (new in ES6)
* Primitives are **immutable** and can only be reassigned a new value.
  - Note 1: Do <ins>NOT</ins> confuse the primitive itself to the variable assigned to the primitive value.
  - Note 2: commonly referred to as "assign by copy" or "assign by value-copy"

#### String Methods

* `.join()`
* `.split('')`
* `toUpperCase()`
* `toLowerCase()`
* `join('')`

* [.indexOf()](https://www.w3schools.com/jsref/jsref_indexof.asp)

#### What is the difference between null and undefined?

##### What is `null`?
Two features to understand:
* `null` is an empty or non-existent value
* `null` must be assigned

```javascript
let a = null
console.log(a) // null
```

##### What is `undefined`?
* `undefined` usually means a variable has been declared, but not defined

```javascript
let b
console.log(b) // undefined
```

#### `typeof` keyword

TK

``` javascript
let a = null
let b
console.log(typeof a) // object
console.log(typeof b) // undefined 
```

### Type Coercion 

#### Explicit Coercion

TK

#### Implicit Coercion

* Surrounding Context
  -Since JS si a weakly-typed languages, values can be converted between different types automatically. 
  - Occurs usually when operators are applied to different types (e.g.,)
* `==`: 
```javascript
\\ `==` is much less predictable than `===` 
console.log(5 == 5) // true
console.log(5 == '5') // true
console.log(true == 'true') // false
console.log('1' == true) // true 
```
### Loosely vs. Strictly Equal (`==` vs. `===`)

* Loose equality: Compare two values for equality after converting both values to a common type. 
* Strict equality: Comparing two values for equality, neither value is implicitly converted to some other value before being compared. 


#### References

* [Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)


#### Truthiness and Falsiness 

* **always falsy**: `false`, `0`, `''` or `""` (empty string), `null`, `undefined`, `NaN`
* **truthy**: everything else including `'0'`, `'false'`, `[]` (empty array), `{}` (empty object), `function(){}` (an 'empty' function)

##### Shortcuts
* `!`: not operator 
* `!!`: Putting double bang in front of something will give you its truthiness
* **Other Logical Operators** (e.g., `&&`, `||`)


#### How many types of objects are there?

TK

### Arrays

#### What is an Array? 

* list-like data structure in Javascript

#### Properties
* `.indexOf`
* `.length` - returns property for the number of elements

#### Methods (TK - go  back and state which ones are immutable and mutable)
* `.push()` method - adds to the end of an array
* `.pop()` method - removes and returns the the most recent element popped off
* `.shift`
* `.slice`
* `.reverse`

* `.splice(index, count [optional], inputElements [optional])` - mutates the original array by adding or removing elemnts from the middle of an array (rather than from either end) and returns the original array with those elements removed  
* `concat`

TK TK TK - find place

#### Mutators
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

#### Nested Arrays 

TK

#### References

* [Primitive MDN Page](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)
* [Javascipt - Null vs. Undefined](https://codeburst.io/javascript-null-vs-undefined-20f955215a2)
* [Explaining Value vs. Reference in Javascript](https://codeburst.io/explaining-value-vs-reference-in-javascript-647a975e12a0)
* [Parameters & Arguments in JavaScript](https://codeburst.io/parameters-arguments-in-javascript-eb1d8bd0ef04)

TK TK TK - find place end


```javascipt
exampleString = 'abaacdade'
const frequencyCounter = (string) => {
  const recordedChars = {}
  const charArr = string.split('')
  for (let i=0; i<charArr.length; i++){
    if (recordedChars[charArr[i]] > 0){
      recordedChars[charArr[i]] = recordedChars[charArr[i]] + 1
    }
    else{
      recordedChars[charArr[i]] = 1
    }
  }
  return recordedChars
}

console.log(frequencyCounter(exampleString))
```

### Objects

* an object is a collection of key-value pairs

#### Bracket vs. Dot Notation

* bracket notation needs quotes to access key unless you are intentionally accessing the variable that contains the key name

### for... in loop

#### Wrapper Objects


## Control Flow in Javascript

### What is control flow? 

* It's the order in which the computer executes statements in a script. 
* Code is run in order from the first line in the file to the last line unless a computer comes across structures that can change control flow, such as conditionals and loops

### Conditionals

#### Conditional Statements in JS
* `if`: directs to block of code below if `true`
* `else`: directs to block of code below if `false`
* `else if`: directs to block of code below if `true` and above conditional statements are `false`
* `switch`: matches the expression's value to a case `clause` and executes statements associated with the case 

```javascript
if (condition1) {
  //  block of code to be executed if condition1 is true
} else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
} else {
  //  block of code to be executed if the condition1 is false and condition2 is false
}
```

```javascript
switch (expression) {
  case value1:
    //Statements executed when the
    //result of expression matches value1
    [break;]
  case value2:
    //Statements executed when the
    //result of expression matches value2
    [break;]
  ...
  case valueN:
    //Statements executed when the
    //result of expression matches valueN
    [break;]
  [default:
    //Statements executed when none of
    //the values match the value of the expression
    [break;]]
}
```

#### Ternaries
* shortcut for the `if` statement
* for `false` statements, the condition could be expressions: `null`, `NaN`, `0`, the empty string (`""`), and `undefined`
```javascript
// syntax example 1
condition ? exprIfTrue : exprIfFalse

// syntac example 2
function example(…) {
    return condition1 ? value1
         : condition2 ? value2
         : condition3 ? value3
         : value4;
}

// equivalent to:
function example(…) {
    if (condition1) { return value1; }
    else if (condition2) { return value2; }
    else if (condition3) { return value3; }
    else { return value4; }
}
```

### Loops
* `while`: loop with (1) `while` keyword, (2) conditional expression that evaluates to a boolean, (3) a code block that eventually makes a base condition to exit the loop
```javascript
// initialization outside of loop
while(// condition){
 // code block with update (note: update should go to a final state that breaks out of the loop)
}

// example 
let i=0
while(i<5){
 console.log('hi')
 i++
}
```
 
* `for`: loop with (1) `for` keyword, (2) three optional expressions, (3) a code block
 
``` javascript
// for (initialization; condition; update){
//  code block
// }

// example -- note: similar to `while`, these three fields can do a lot more
for (let i=0; i < 5; i++){
 console.log('hi')
}
```
* `continue`: jumps over one iteration in the loop and checks the next loop
* `break`: jumps out of the loop
  
#### References
* [JavaScript type coercion explained](https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/)
* [Control Flow MDN Page](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)
* [JavaScript Switch Statement](https://www.w3schools.com/js/js_switch.asp)
* [switch MDN Page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
* [Conditional (ternary) operator](https://developer.mozilla.org/en US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
* [JavaScript — Null vs. Undefined](https://codeburst.io/javascript-null-vs-undefined-20f955215a2)

### Scope
#### What is *Scope*?
Scope determines the accessibility of identifiers (e.g., variables) based off where it was created.

Note: JavaScript is lexically scoped

#### What is *Lexical Scope*?
* Lexical Scope means the location where a variable is declared determines its scope (see [Variable Declaration](#variable-declaration))

#### What is *Global Scope*?
* Global Scope is when a variable declaration is made outside of a function and can be referenced throughout a file

Note: `window` is the global object in the browser 

#### What is *Functional Scope*?

* Variable declarations inside of functions are 'locally scoped'

#### What if a variable is defined locally and globally? 

* **Variable Shadowing**: 

TK - https://en.wikipedia.org/wiki/Variable_shadowing

#### What is *Block Scope*?

* any block of code (code inside curly braces) has its own scope
Note: must use `let` rather than `var` to maintain block scope

TK

## Features of ES6

ECMAScript is the Javacript's language standard (e.g.,ES6 (ES2015), ES2019)

### Variable Declaration (see above)
 
### Template Literals
Template literals can be used to avoid concatenating strings or expressions.

```javascript
function helloWorld(name){
 return `Hi ${name}!`
}

// same example with template literals
function combiningGroups(groupsize1, groupsize2){
 return `The new group has ${groupsize1 + groupsize2} people.`
}
```

### Arrow Functions
A slightly different way of declaring a function that is shorter syntactically and binds `this` to its enclosing execution context.


```javascript
// arrow function
const milesToWalk = (miles) => {
 return miles + 500
}

// original function declaration
function milesToWalk(miles){
 return miles + 500
}
```

### Symbol Primitive

TK

#### References
* [const MDN Page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) and [let MDN Page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
* [Template literals (Template strings)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
* [Arrow functions MDN Page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

---
### Misc - Put Somewhere

#### Advanced Use of Context: `this` keyword
#### References
* [Eyeballing-this.md](https://gist.github.com/zcaceres/2a4ac91f9f42ec0ef9cd0d18e4e71262)
* []()

#### What is the difference between a parameter and an argument? 
* **parameter** - the placeholder listed for potential variables when defining a function
* **argument** - the actual value passed to the function when that function is invoked

#### Closure

**i. What is closure?**

Good Defn: the combination of a function bundled together (enclosed) with references to its surrounding state (lexical environment) 

Layman's Terms: access to an outer function’s scope from an inner function

**ii. How is closure used?**

#### Currying


#### References
* [How to understand the keyword this and context in JavaScript](https://www.freecodecamp.org/news/how-to-understand-the-keyword-this-and-context-in-javascript-cd624c6b74b8/)
* [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
* [Understanding Scope and Context in JavaScript](http://ryanmorr.com/understanding-scope-and-context-in-javascript/)
* [Understanding JavaScript 'this' keyword (Context)](https://medium.com/datadriveninvestor/javascript-context-this-keyword-9a78a19d5786)
* [The many faces of `this` in javascript](https://blog.pragmatists.com/the-many-faces-of-this-in-javascript-5f8be40df52e)
* [What is JavaScript Interview: What is Closure?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)
* [Understanding Currying in JavaScript](https://blog.bitsrc.io/understanding-currying-in-javascript-ceb2188c339)

---

### `eventListeners`

TK 

### The Different Engines 

QuickSort for Chrome, but it's a bit nuanced . Chrome's v8 engine uses a combination of QuickSort and InsertionSort for arrays (length < 10). Mozilla Firefox's SpiderMonkey uses MergeSort for stability.


#### Merge Sort 


#### References 
* [Merge Sort Algorithm in JavaScript](https://medium.com/javascript-in-plain-english/javascript-merge-sort-3205891ac060)
---

### General Dictionary

currying
execute
[deobfuscate](https://www.techopedia.com/definition/24827/deobfuscate)
instantiate 

---
# NERD Study Guide

Why does this thing exist? Which problems does it solve/create? 

## React

### Architecture 



### Virtual DOM


-- Shadow DOM on drawbacks

#### References
* [Virtual DOM and Internals](https://reactjs.org/docs/faq-internals.html)

## Redux
<p align="center">
<img src="https://miro.medium.com/max/2532/1*zOCTZhMGZhE84_OSU7k9ig.jpeg" alt="Image of Redux Flow"  width="400"/>
</p>

### What is Redux?

A state management library that holds and updates the entire state by providing it in a read-only store

Pros: Properties don’t dictate structure (in relation to React)

Cons: Sometimes used unnecessarily, other forms of storage do exist for caching and media delivery

### Actions

* An object that is returned by a pure function with no side-effects
* It contains the "type" and updates to the state
* Sent to the store using dispatch() and the store updates the state using the info provided in the action

### Reducer

* Pure function that takes the current state and action and performs a state update
* Usually in the form of a switch statement that takes in the `action.type` and creates a new state with this action

<ins>Example</ins> 

### Store

* Holds the entire state in a single object <ins>acting as a single source of truth</ins>
* Assign it a vairable using `createStore(combinedReducer)`
* Store passes two arguments to the reducer (previous state and the action) 

### Thunks

#### Why use Thunks?

We want everything that takes a long time to occur in one central place. Having the time issues in one place makes our life easier. 


#### References
* [Redux Logic Flow — Crazy Simple Summary](https://levelup.gitconnected.com/redux-logic-flow-crazy-simple-summary-35416eadabd8)

## HTML

## CSS 

## Javascript Runtime Environments

### What is Node? 

* A runtime environment software that allows the ability to execute JavaScript programs directly on your operating system outside of the browser (Note: similar to how JavaScript executed in the browser has access to the DOM (e.g., `document`, `window`))
* JS programs using `node` can perform OS-specific functionality such as read/write from files or establish network connections (e.g., `__dirname`)
* Node's package manager (`npm`) is similar to `pip` in Python, `gem` in Ruby, `brew` in Unix, and `apt` in Linux

### Event Loop

#### Overview
The asynchronous, single-threaded nature is not built into the JS language, but it's built on the core JS language inside the browser (or the programming environment) and accessed using the browser API's. 
<p align="center">
<img src="https://miro.medium.com/max/1504/1*7GXoHZiIUhlKuKGT22gHmA.png" alt="Image of Basic Architecture"  width="400"/>
</p>

* **Heap** - a large mostly unstructured region of memory where objects are allocated
* **Call Stack** - a representation of the single thread provided for JS code execution 
* **Browser or Web API's** - these components are built into the web browser (or the computer environment) to provide extra functionality on top of JS (Note: the point of the API's is to abstract away the complexity involved and provide the extra capabilities)

[![What the heck is the event loop anyway? video](https://raw.githubusercontent.com/djchinia/javascript-study-guide/async-await/media/eventLoop.png)](https://youtu.be/8aGhZQkoFbQ?t=790)

#### Blocking

Things that are slow and on that stack (TK). 

#### Concurrency & the Event Loop 

The browser is more than the runtime and similarly in node (there's extra things in C) (TK)

#### Promises vs. Async/Await

a promise is a returned object you attach callbacks to, instead of passing callbacks into a function
-- promise constructor takes in one argument: a callback function with two parameters — resolve and reject.

“async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.

The keyword await makes JavaScript wait until that promise settles and returns its result.

```javascript
async function f() {

  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });

  let result = await promise; // wait till the promise resolves (*)

  alert(result); // "done!"
}

f();
```

#### References
* [Ryan Dahl: Original Node.js presentation](https://www.youtube.com/watch?v=ztspvPYybIY)
* [JavaScript: Promises explained with simple real life analogies](https://codeburst.io/javascript-promises-explained-with-simple-real-life-analogies-dd6908092138)
* [Async/await](https://javascript.info/async-await)
* [Concurrency model and the event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)
* [Event Loop Explained](https://medium.com/front-end-weekly/javascript-event-loop-explained-4cd26af121d4)
* [Asynchronous JavaScript: From Callback Hell to Async and Await](https://blog.hellojs.org/asynchronous-javascript-from-callback-hell-to-async-and-await-9b9ceb63c8e8)
* [Understanding JS: The Event Loop](https://hackernoon.com/understanding-js-the-event-loop-959beae3ac40)
* [Art of Node](https://github.com/maxogden/art-of-node#streams)


---


### Garbage Collection

- Pass by reference

#### References
* [Garbage Collection](https://javascript.info/garbage-collection)

## Express

### Express API

### Postman

#### References
* [Express](http://expressjs.com/en/4x/api.html)
* [Build a RESTful API Using Node and Express 4](https://scotch.io/tutorials/build-a-restful-api-using-node-and-express-4)

## SQL

### Basic Commands

### The DBMS

The Database Management System is responsible for translating declarative queries into concrete file system operations

### `psql` client

### `pg` client

### Differences between Postgres and MySQL

### Useful Practice
* [PostgreSQL Exercises](https://pgexercises.com/)
* [PostgreSQL Tutorial](http://www.postgresqltutorial.com/)

#### References
* [PostgreSQL vs MySQL: What's the Difference?](https://www.guru99.com/postgresql-vs-mysql-difference.html)

## Sequelize (Object Relational Mapping)

* [Why you should avoid ORMs (with examples in Node.js)](https://blog.logrocket.com/why-you-should-avoid-orms-with-examples-in-node-js-e0baab73fa5/)

### Eager Loading vs. Lazy Loading

## Webpack
<p align="center">
<img src="https://miro.medium.com/max/2292/1*3JthPwVK_yFrZ4ACi0LZyw.png" alt="Image of Webpack"  url="https://medium.com/ag-grid/webpack-tutorial-understanding-how-it-works-f73dfa164f01" width="400"/>
</p>

"Webpack is a module bundler. It takes disparate dependencies, creates modules for them and bundles the entire network up into manageable output files. This is especially useful for Single Page Applications (SPAs)."

#### Referenes
* [Webpack Tutorial: Understanding How It Works](https://medium.com/ag-grid/webpack-tutorial-understanding-how-it-works-f73dfa164f01)

## Babel

### What is Babel? 
* a toolchain used to convert ES2015+ code into a backwards compatible version of JS in current and older browsers and environments

### What can Babel do?
* Transform syntax
* Polyfill features that are missing in the original environment 
* Source code transformations (i.e., codemods)
* [Other Features](https://babeljs.io/videos.html)

### [Example of Babel Transpiling](https://babeljs.io/docs/en/index.html)
```javascript
// Babel Input: ES2015 arrow function
[1, 2, 3].map((n) => n + 1);

// Babel Output: ES5 equivalent
[1, 2, 3].map(function(n) {
  return n + 1;
});
```

### [Benefits of Babel in ES6](https://coherent-labs.com/posts/es6-standard-with-babel-js/)
1. Block scoped variables - see `let` keyword
2. Classes - TK 
3. Promises - TK
4. Modules - can now import/export multiple named values

#### Reference 
* [What is Babel?](https://babeljs.io/docs/en/index.html)
* [Videos about Babel](https://babeljs.io/videos.html)
* [How to use ES6 standard with Babel.js](https://coherent-labs.com/posts/es6-standard-with-babel-js/)

## Topics for Another Day 
* [MVC Pattern](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
* [Test-Driven Development](https://www.youtube.com/watch?v=6pYUzEduLyU)
* Debugging + Chrome Console
* [WebAssembly](https://hacks.mozilla.org/2017/02/a-cartoon-intro-to-webassembly/)
