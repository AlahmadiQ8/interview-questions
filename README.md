# General Interview Questions



## Table of Contents

* [General Javascript](#general-javascript)
  * [Write a function that sums a variable number of arguments\. Then apply the function to sum an array](#write-a-function-that-sums-a-variable-number-of-arguments-then-apply-the-function-to-sum-an-array)
  * [Implement class inheritance in vanilla javascript](#implement-class-inheritance-in-vanilla-javascript)
  * [Can you name two programming paradigms important for JavaScript app developers?](#can-you-name-two-programming-paradigms-important-for-javascript-app-developers)
  * [What is functional programming?](#what-is-functional-programming)
  * [What are two\-way data binding and one\-way data flow, and how are they different?](#what-are-two-way-data-binding-and-one-way-data-flow-and-how-are-they-different)
  * [What is asynchronous programming, and why is it important in JavaScript?](#what-is-asynchronous-programming-and-why-is-it-important-in-javascript)
  * [What is prototypal inheritance?](#what-is-prototypal-inheritance)
  * [An Object](#an-object)
  * [Prototype Chain](#prototype-chain)
  * [Constructor](#constructor)
* [Javascript Puzzle Questions](#javascript-puzzle-questions)
  * [Write a function that can determine whether a string is a palindrome in under 100 characters](#write-a-function-that-can-determine-whether-a-string-is-a-palindrome-in-under-100-characters)
  * [How would you empty the array var arr = [1,2,3,4]?](#how-would-you-empty-the-array-var-arr--1234)
  * [Write a mul function which mul(2)(3)(4) = 24](#write-a-mul-function-which-mul234--24)
  * [Prototypal Inheritance \- What will be the output of the code below?](#prototypal-inheritance---what-will-be-the-output-of-the-code-below)
* [MongoDb Questions](#mongodb-questions)
  * [Schema design example](#schema-design-example)
  * [Command to insert a document in a database called school and collection called persons\.](#command-to-insert-a-document-in-a-database-called-school-and-collection-called-persons)
  * [Mention the command to list all the indexes on a particular collection](#mention-the-command-to-list-all-the-indexes-on-a-particular-collection)
* [Web Related Questions (REST, Security etc\.)](#web-related-questions-rest-security-etc)
  * [State The Core Components Of An HTTP Request](#state-the-core-components-of-an-http-request)
  * [State The Core Components Of An HTTP Response](#state-the-core-components-of-an-http-response)
  * [Explain The Caching Mechanism?](#explain-the-caching-mechanism)
  * [Authentication \- What are JWTs?](#authentication---what-are-jwts)
  * [Authentication \- Where to store Session IDs, tokens?](#authentication---where-to-store-session-ids-tokens)
  * [What is statelessness in RESTful Webservices?](#what-is-statelessness-in-restful-webservices)
  * [Common Headers](#common-headers)
  * [Cache Control Directives](#cache-control-directives)
  * [What are the best practices to be followed while designing a secure RESTful web service?](#what-are-the-best-practices-to-be-followed-while-designing-a-secure-restful-web-service)
  * [HTTP Status Codes](#http-status-codes)






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
Only the model has the access to change the app’s state. The effect is that data 
always flows in a single direction, which makes it easier to understand.

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

### What is prototypal inheritance?

In a classical language, classes typically define the structure of objects, but 
in a prototypal language, the objects themselves define their structure, and 
this structure can be inherited and modified by other objects at runtime.

Prototypal inheritance first appeared in Self and has since appeared in many 
other languages, but these days most people think of JavaScript when they think 
of prototypal inheritance.

### An Object


```javascript
var foo = {
  x: 10,
  y: 20
};
```

![](http://dmitrysoshnikov.com/wp-content/uploads/basic-object.png)

[source](http://dmitrysoshnikov.com/ecmascript/javascript-the-core/)

### Prototype Chain


```javascript
var a = {
  x: 10,
  calculate: function (z) {
    return this.x + this.y + z;
  }
};
 
var b = {
  y: 20,
  __proto__: a
};
 
var c = {
  y: 30,
  __proto__: a
};

// The above is equivelant to 
// var b = Object.create(a, {y: {value: 20}});
// var c = Object.create(a, {y: {value: 30}});
 
// call the inherited method
b.calculate(30); // 60
c.calculate(40); // 80
```

![](http://dmitrysoshnikov.com/wp-content/uploads/prototype-chain.png)

[source](http://dmitrysoshnikov.com/ecmascript/javascript-the-core/)


### Constructor

Besides creation of objects by specified pattern, a constructor function does 
another useful thing — it automatically sets a prototype object for newly created 
objects. This prototype object is stored in the ConstructorFunction.prototype 
property.

E.g., we may rewrite previous example with b and c objects using a constructor 
function. Thus, the role of the object a (a prototype) Foo.prototype plays:

```javascript
// a constructor function
function Foo(y) {
  // which may create objects
  // by specified pattern: they have after
  // creation own "y" property
  this.y = y;
}
 
// also "Foo.prototype" stores reference
// to the prototype of newly created objects,
// so we may use it to define shared/inherited
// properties or methods, so the same as in
// previous example we have:
 
// inherited property "x"
Foo.prototype.x = 10;
 
// and inherited method "calculate"
Foo.prototype.calculate = function (z) {
  return this.x + this.y + z;
};
 
// now create our "b" and "c"
// objects using "pattern" Foo
var b = new Foo(20);
var c = new Foo(30);
 
// call the inherited method
b.calculate(30); // 60
c.calculate(40); // 80
 
// let's show that we reference
// properties we expect
 
console.log(
 
  b.__proto__ === Foo.prototype, // true
  c.__proto__ === Foo.prototype, // true
 
  // also "Foo.prototype" automatically creates
  // a special property "constructor", which is a
  // reference to the constructor function itself;
  // instances "b" and "c" may found it via
  // delegation and use to check their constructor
 
  b.constructor === Foo, // true
  c.constructor === Foo, // true
  Foo.prototype.constructor === Foo, // true
 
  b.calculate === b.__proto__.calculate, // true
  b.__proto__.calculate === Foo.prototype.calculate // true
 
);
```

![](http://dmitrysoshnikov.com/wp-content/uploads/constructor-proto-chain.png)

[Source](http://dmitrysoshnikov.com/ecmascript/javascript-the-core/)


## Javascript Puzzle Questions

### Write a function that can determine whether a string is a palindrome in under 100 characters

```javascript
function isPalindrome(str) {
  return (str.toLowerCase() == str.split('').reverse().join(''));
}
```

[Source](https://www.upwork.com/i/interview-questions/javascript/)

### How would you empty the array ```var arr = [1,2,3,4]```?

```javascript
arr.length = 0;

arr.splice(0, arr.length);

while(arr.length){
    arr.pop();
}

arr = []
```

[Source](https://www.upwork.com/i/interview-questions/javascript/)


### Write a ```mul``` function which ```mul(2)(3)(4) = 24```

```javascript
function mul (x) {
  return function (y) { // anonymous function 
    return function (z) { // anonymous function 
      return x * y * z; 
    };
  };
}
```


### Prototypal Inheritance - What will be the output of the code below? 

```javascript
var Employee = {
  company: 'xyz'
}
var emp1 = Object.create(Employee);
delete emp1.company
console.log(emp1.company);
```

The output would be ```xyz```. Here, ```emp1``` object has ```company``` as its prototype property. 
The ```delete``` operator doesn't delete prototype property.

emp1 object doesn't have company as its own property. You can test it 
```console.log(emp1.hasOwnProperty('company')); //output : false```. 
However, we can delete the company property directly from the ```Employee``` object 
using ```delete Employee.company```. Or, we can also delete the ```emp1``` object using the 
```__proto__``` property ```delete emp1.__proto__.company```.

[Source](https://www.codementor.io/nihantanu/21-essential-javascript-tech-interview-practice-questions-answers-du107p62z)


## MongoDb Questions

### Schema design example

* Library Management Application 
  * Patrons/Users
  * Books
  * Authors
  * Publishers

```javascript 
db.patrons.find({_id: "joe"})
{
  _id: "joe",
  name: "Joe Bookreader",
  FavoriteGenres: ['mystery', 'programming'],
  address: {
    street: '123 Fake St.',
    city: "Faketown",
    state: "MA",
    zip: "12345"
  }
}
```

### Command to insert a document in a database called school and collection called persons.

```javascript
db.persons.insert( { name: 'mohammad', dept: 'EE' })
```

### Mention the command to list all the indexes on a particular collection

```javascript
db.collection.getIndexes()
```

## Web Related Questions (REST, Security etc.)

### State The Core Components Of An HTTP Request

Each HTTP request includes five key elements:

1. **Verb** − Indicate HTTP methods such as GET, POST, DELETE, PUT etc.
2. **URI** − Uniform Resource Identifier (URI) to identify the resource on server.
3. **HTTP** Version − Indicate HTTP version, for example HTTP v1.1 .
4. **Request Header** − Contains metadata for the HTTP Request message as key-value pairs. For example, client ( or browser) type, format supported by client, format of message body, cache settings etc.
5. **Request Body** − Message content or Resource representation.

[Source](http://www.techbeamers.com/rest-api-interview-questions-answers/)

### State The Core Components Of An HTTP Response

Every HTTP response includes four key elements:

1. Status/Response Code – Indicates Server status for the resource present in the HTTP request.For example, 404 means resource not found and 200 means response is ok.
2. HTTP Version – Indicates HTTP version, for example-HTTP v1.1.
3. Response Header – Contains metadata for the HTTP response message stored in the form of key-value pairs. For example, content length, content type, response date, and server type.
4. Response Body – Indicates response message content or resource representation.

[Source](http://www.techbeamers.com/rest-api-interview-questions-answers/)

### Explain The Caching Mechanism?

Caching is a process of storing server response at the client end. It makes the 
server save significant time from serving the same resource again and again.

The server response holds information which leads a client to perform the caching. 
It helps the client to decide how long to archive the response or not to store it at all.

[Source](http://www.techbeamers.com/rest-api-interview-questions-answers/)

### Authentication - What are JWTs?

JSON Web Tokens. It's a solution for API Authentication and OAuth2. 

### Authentication - Where to store Session IDs, tokens?

You can store in localStorage/sessionStorage or in cookies. Since Javascript have 
access to the web storage, it can be less secure and vulnerable to 
**cross-site scripting (XSS)** attacks. 

But with cookies, you can set ```HttpOnly``` cookie flag to prevent javascript from 
accessing the cookie. 

### What is statelessness in RESTful Webservices?

As per REST architecture, a RESTful web service should not keep a client state 
on server. This restriction is called statelessness. It is responsibility of the 
client to pass its context to server and then server can store this context to 
process client's further request. For example, session maintained by server is 
identified by session identifier passed by the client.

[Source](https://www.tutorialspoint.com/restful/restful_interview_questions.htm)

### Common Headers 

Header | Description
--- | ---
**Date** | represents the date and time at which the message was originated
**Cache-Control** | Used to specify directives that MUST be obeyed by all caching mechanisms along the request/response chain
**Last-Modified** | Indicates the date and time at which the origin server believes the variant was last modified
**Location** | For 201 (Created) responses, the Location is that of the new resource which was created by the request. For 3xx responses, the location SHOULD indicate the server's preferred URI for automatic redirection to the resource. The field value consists of a single absolute URI.
**Content-Type** | The Content-Type entity-header field indicates the media type of the entity-body sent to the recipient or, in the case of the HEAD method, the media type that would have been sent had the request been a GET.
**Host** | The Host request-header field specifies the Internet host and port number of the resource being requested, as obtained from the original URI given by the user or referring resource
**Accept** | The Accept request-header field can be used to specify certain media types which are acceptable for the response. Accept headers can be used to indicate that the request is specifically limited to a small set of desired types, as in the case of a request for an in-line image.

[Source](http://www.restpatterns.org/HTTP_Headers)

### Cache Control Directives

```
cache-request-directive =
       "no-cache"                          ; Section 14.9.1
     | "no-store"                          ; Section 14.9.2
     | "max-age" "=" delta-seconds         ; Section 14.9.3, 14.9.4
     | "max-stale" [ "=" delta-seconds ]   ; Section 14.9.3
     | "min-fresh" "=" delta-seconds       ; Section 14.9.3
     | "no-transform"                      ; Section 14.9.5
     | "only-if-cached"                    ; Section 14.9.4
     | cache-extension                     ; Section 14.9.6

cache-response-directive =
     "public"                               ; Section 14.9.1
   | "private" [ "=" <"> 1#field-name <"> ] ; Section 14.9.1
   | "no-cache" [ "=" <"> 1#field-name <"> ]; Section 14.9.1
   | "no-store"                             ; Section 14.9.2
   | "no-transform"                         ; Section 14.9.5
   | "must-revalidate"                      ; Section 14.9.4
   | "proxy-revalidate"                     ; Section 14.9.4
   | "max-age" "=" delta-seconds            ; Section 14.9.3
   | "s-maxage" "=" delta-seconds           ; Section 14.9.3
   | cache-extension                        ; Section 14.9.6
```

[Source](http://www.restpatterns.org)

### What are the best practices to be followed while designing a secure RESTful web service?

**Validation** − Validate all inputs on the server. Protect your server against SQL or NoSQL injection attacks.
**Session based authentication** − Use session based authentication to authenticate a user whenever a request is made to a Web Service method.
**No sensitive data in URL** − Never use username, password or session token in URL , these values should be passed to Web Service via POST method.
**Restriction on Method execution** − Allow restricted use of methods like GET, POST, DELETE. GET method should not be able to delete data.
**Validate Malformed XML/JSON** − Check for well formed input passed to a web service method.
**Throw generic Error Messages** − A web service method should use HTTP error messages like 403 to show access forbidden etc.

[Source](https://www.tutorialspoint.com/restful/restful_interview_questions.htm)


### HTTP Status Codes 

```
200 - OK
201 - Created
202 - Accepted
204 - No Content
400 - Bad Request
401 - Unauthorized
402 - Payment Required
403 - Forbidden
404 - Not Found
405 - Method Not Allowed
500 - Internal Server Error
```

[Source](http://www.restpatterns.org/HTTP_Status_Codes)


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