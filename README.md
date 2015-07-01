# Javascript
Understanding Javascript better

## Table of Contents
1. [Functions](#functions)
1. [Prototype](#prototype)

## Functions
- [1.1](#1.1) <a name='1.1'></a> **Different Functions Definitions**: 
```javascript
  // Function Declaration is parsed from the start
  // Function Declarations loads before any code is executed (Hoisting)
  // Semicolons are used to separate executable JavaScript statements
  // Function declaration is not an executable statement, it is not common to end it with a semicolon
  function functionName(a) {
    return a;
  }

  // Function Expression is stored in a variable and defined at run-time
  // The function here is actually anonymous function
  // Functions stored in variables do not need function names. 
  // They are always invoked (called) using the variable name.
  var x = function (a) {
    return a;
  };
  
  // Function() Constructor
  // Notice this is not the 'normal' constructor, but the costructor for function
  // To create function object, notice we use the keyword "Function" and "new"
  var functionName = new Function("a", "return a");
  
```

- [1.2](#1.2) <a name='1.2'></a> **Interesting case: Function and Object**:
```javascript
  // Constructor Pattern 
  // And the firstMethod and secondMethod will be assigned to the window object from the start
  var app1 = function(){
    this.firstMethod = function(){
       //something
    };
    this.secondMethod = function(){
       //something
    };
  };
  
  // Object Literal
  // TODO Why Object Literal does not closure?        
  // Refer to: http://www.akawebdesign.com/2010/10/22/javascript-singletons-object-literals-vs-closures/
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
