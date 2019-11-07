# Javascript Study Guide
- [The Basics](#the-basics)
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
- [Express](#express)
- [Node](#node)
- [SQL](#sql)


# Javascript Study Guide
## The Basics



### Loosely vs. Strictly Equal

* Loose equality: Compare two values for equality after converting both values to a common type. 
* Strict equality: Comparing two values for equality, neither value is implicitly converted to some other value before being compared. 


#### References

* [Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)

### Context and Scope

#### Context

Scope - determines the accessibility of identifiers (e.g., variables) based off where it was created

Note: `window` is the global object in the browser 

TK

#### Scope

TK

#### `this` keyword and context

TK

#### Closure

**i. What is closure?**

Good Defn: the combination of a function bundled together (enclosed) with references to its surrounding state (lexical environment) 

Layman's Terms: access to an outer function’s scope from an inner function

**ii. How is closure used?**

#### Currying


#### References
* [How to understand the keyword this and context in JavaScript](https://www.freecodecamp.org/news/how-to-understand-the-keyword-this-and-context-in-javascript-cd624c6b74b8/)
* [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
* [Understanding Scope and Context in Javascript](http://ryanmorr.com/understanding-scope-and-context-in-javascript/)
* [Understanding Javascript 'this' keyword (Context)](https://medium.com/datadriveninvestor/javascript-context-this-keyword-9a78a19d5786)
* [The many faces of `this` in javascript](https://blog.pragmatists.com/the-many-faces-of-this-in-javascript-5f8be40df52e)
* [What is Javasript Interview: What is Closure?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36)
* [Understanding Currying in Javascript](https://blog.bitsrc.io/understanding-currying-in-javascript-ceb2188c339)

---

### Event Loop

#### Overview
The asynchronous, single-threaded nature is not built into the JS language, but it's built on the core JS language inside the browser (or the programming environment) and accessed using the browser API's. 
<p align="center">
<img src="https://miro.medium.com/max/1504/1*7GXoHZiIUhlKuKGT22gHmA.png" alt="Image of Basic Architecture"  width="400"/>
</p>

* **Heap** - a large mostly unstructured region of memory where objects are allocated
* **Stack** - a representation of the single thread provided for JS code execution 
* **Browser or Web API's** - these components are built into the web browser (or the computer environment) to provide extra functionality on top of JS (Note: the point of the API's is to abstract away the complexity involved and provide the extra capabilities)


#### Promises vs. Async/Await

a promise is a returned object you attach callbacks to, instead of passing callbacks into a function
-- promise constructor takes in one argument: a callback function with two parameters — resolve and reject.

“async” before a function means one simple thing: a function always returns a promise. Other values are wrapped in a resolved promise automatically.

The keyword await makes JavaScript wait until that promise settles and returns its result.


<pre><code>async function f() {

  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });

  let result = await promise; // wait till the promise resolves (*)

  alert(result); // "done!"
}

f();
</code></pre>



#### References
* [JavaScript: Promises explained with simple real life analogies](https://codeburst.io/javascript-promises-explained-with-simple-real-life-analogies-dd6908092138)
* [Async/await](https://javascript.info/async-await)
* [Concurrency model and the event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)
* [Event Loop Explained](https://medium.com/front-end-weekly/javascript-event-loop-explained-4cd26af121d4)
* [Asynchronous JavaScript: From Callback Hell to Async and Await](https://blog.hellojs.org/asynchronous-javascript-from-callback-hell-to-async-and-await-9b9ceb63c8e8)
* [Understanding JS: The Event Loop](https://hackernoon.com/understanding-js-the-event-loop-959beae3ac40)


---


### Garbage Collection

- Pass by reference

#### References
* [Garbage Collection](https://javascript.info/garbage-collection)

---

### `eventListeners`

TK 

### The Different Engines 

QuickSort for Chrome, but it's a bit nuanced . Chrome's v8 engine uses a combination of QuickSort and InsertionSort for arrays (length < 10). Mozilla Firefox's SpiderMonkey uses MergeSort for stability.

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



#### References
* [Actions and Reducers](https://rangle.github.io/react-training/redux-action-reducer/)


## Express

## Node

## SQL
