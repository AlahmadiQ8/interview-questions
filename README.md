
Table of Contents
=================

* [General Interview Questions](#general-interview-questions)
  * [General Javascript](#general-javascript)
    * [Write a function that sums a variable number of arguments\. Then apply the function to sum an array](#write-a-function-that-sums-a-variable-number-of-arguments-then-apply-the-function-to-sum-an-array)
    * [Implement class inheritance in vanilla javascript](#implement-class-inheritance-in-vanilla-javascript)
    * [Can you name two programming paradigms important for JavaScript app developers?](#can-you-name-two-programming-paradigms-important-for-javascript-app-developers)
    * [What is functional programming?](#what-is-functional-programming)
    * [What are two\-way data binding and one\-way data flow, and how are they different?](#what-are-two-way-data-binding-and-one-way-data-flow-and-how-are-they-different)
    * [What is asynchronous programming, and why is it important in JavaScript?](#what-is-asynchronous-programming-and-why-is-it-important-in-javascript)


# General Interview Questions

## General Javascript 

### Write a function that sums a variable number of arguments. Then apply the function to sum an array

```javascript
function sum() {
  let res = 0;
  for (let i = 0; i< arguments.length; i++) {
    res += arguments[i];
  }
  return result;
}
sum(1,2,3); // 6
var data = [1,2,3];
sum.apply(null, data); // 6
```

[Source](http://stackoverflow.com/a/2494047/5431968)


### Implement class inheritance in vanilla javascript

```javascript

function Person(first, last) {
  this.name = name;
  this.last = last;
};

Person.prototype.greeting = function() {
  alert('Hi! I\'m ' + this.name.first + '.');
};

var person1 = new Person('Tammi', 'Smith');

function Teacher(first, last, subject) {
  Person.call(this, first, last);
  this.subject = subject;
}

Teacher.prototype = Object.create(Person.prototype);
Teacher.prototype.constructor = Teacher;

var teacher1 = new Teacher('Dave', 'Griffiths', 'mathematics');
```

[Source](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Inheritance)

### Can you name two programming paradigms important for JavaScript app developers?

* Prototypal inheritance (also: prototypes, OLOO).
* Functional programming (also: closures, first class functions, lambdas).

[Source](https://medium.com/javascript-scene/10-interview-questions-every-javascript-developer-should-know-6fa6bdf5ad95)

### What is functional programming?

* Pure functions / function puri
* No shared states & mutable data
* Avoid side-effects
* Simple function composition

[Source](https://medium.com/javascript-scene/10-interview-questions-every-javascript-developer-should-know-6fa6bdf5ad95)

### What are two-way data binding and one-way data flow, and how are they different?

Two way data binding means that UI fields are bound to model data dynamically 
such that when a UI field changes, the model data changes with it and vice-versa.

One way data flow means that the model is the single source of truth. Changes 
in the UI trigger messages that signal user intent to the model (or “store” in React). 
Only the model has the access to change the app’s state. The effect is that data always flows in a single direction, which makes it easier to understand.

[Source](https://medium.com/javascript-scene/10-interview-questions-every-javascript-developer-should-know-6fa6bdf5ad95)

### What is asynchronous programming, and why is it important in JavaScript?

Synchronous programming means that, barring conditionals and function calls, 
code is executed sequentially from top-to-bottom, blocking on long-running tasks 
such as network requests and disk I/O.

Asynchronous programming means that the engine runs in an event loop. When a 
blocking operation is needed, the request is started, and the code keeps running 
without blocking for the result. When the response is ready, an interrupt is fired, 
which causes an event handler to be run, where the control flow continues. 
In this way, a single program thread can handle many concurrent operations.

[Source](https://medium.com/javascript-scene/10-interview-questions-every-javascript-developer-should-know-6fa6bdf5ad95)


<!-- ### Basic JS programmming

* Scope of variable
* What is Associative Array? How do we use it?

### OOPS JS

* Difference between Classic Inheritance and Prototypical Inheritance
* What is difference between private variable, public variable and static variable? How we achieve this in JS?
* How to add/remove properties to object in run time?
* How to achieve inheritance ?
* How to extend built-in objects?
* Why extending array is bad idea?

### DOM and JS

* Difference between browser detection and feature detection
* DOM Event Propagation
* Event Delegation
* Event bubbling V/s Event Capturing

###Misc

Graceful Degradation V/s Progressive Enhancement


 -->