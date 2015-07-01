# Javascript
Understanding Javascript better

## Table of Contents
1. [Functions](#functions)
1. [Prototype](#prototype)

## Functions
- [1.1](#1.1) <a name='1.1'></a> **Different Functions Definitions**: 
```javascript
  // The named function declaration is parsed from the start
  // Semicolons are used to separate executable JavaScript statements
  // Function declaration is not an executable statement, it is not common to end it with a semicolon
  function myFunction(a, b) {
    return a + b;
  }

  // The function expression is stored in a variable and defined at run-time
  var functionName = function() {}
```

- [1.2](#1.2) <a name='1.2'></a> **Difference between Constructor Function and Object**:
```javascript
  var app1 = function(){
    this.firstMethod = function(){
       //something
    };
    this.secondMethod = function(){
       //something
    };
  };
  
  var app2 = {
    firstKey: function(){
       //something
    },
    secondKey: function(){
       //something
    }
};
```
**[⬆ back to top](#table-of-contents)**

## Prototype
- [2.1](#2.1) <a name='2.1'></a> **Constructor Function and Prototype Object**:
  ![server diagram](Constructor%20and%20Prototype.png)
    1. When we create a function like function Foo() {}, JavaScript creates a Function instance.
    2. Every Function instance (the constructor function) has a property prototype which is a pointer.
    3. The prototype property of the constructor function points to its prototype object.
    4. The prototype object has a property constructor which is also a pointer.
    5. The constructor property of the prototype object points back to its constructor function.
    6. When we create a new instance of Foo like new Foo(), JavaScript creates a new object.
    7. The internal [[proto]] property of the instance points to the prototype of the constructor.
