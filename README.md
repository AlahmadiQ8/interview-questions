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





### Basic JS programmming

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


