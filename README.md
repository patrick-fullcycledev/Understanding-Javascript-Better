# Javascript
Understanding Javascript better

## Table of Contents
1. [Function](#function)
1. [Closure](#closure)
1. [Prototype](#prototype)
1. [Object](#object)
1. [Pattern](#pattern)

## Function
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

- [1.2](#1.2) <a name='1.2'></a> **Interesting case: Function and Object**
```javascript
  // Object literals don't provide closures, only functions do. 
  // In addition, the properties of app1 will not be assigned until the function is called in the first example, 
  // but will be immediately for app2

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
  // TODO Why Object Literal does not have closure?        
  // Refer to: http://www.akawebdesign.com/2010/10/22/javascript-singletons-object-literals-vs-closures/
  var app2 = {
    firstKey: function(){
       //something
    },
    secondKey: function(){
       //something
    }
  };
  
  // Object literal vs Constructor Prototype
  // Refer to: http://stackoverflow.com/questions/17260603/object-literal-vs-constructorprototype
  
```
- [1.3](#1.3) <a name='1.3'></a> **Passed by Value or by Reference**


http://stackoverflow.com/questions/518000/is-javascript-a-pass-by-reference-or-pass-by-value-language

http://eloquentjavascript.net/03_functions.html

http://elegantcode.com/2010/10/22/basic-javascript-part-1-functions/

http://www.w3schools.com/js/js_function_definition.asp

http://stackoverflow.com/questions/4559207/difference-between-a-constructor-and-an-object

**[⬆ back to top](#table-of-contents)**



## Closure
http://howtonode.org/why-use-closure

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

http://spin.atomicobject.com/2014/10/20/javascript-scope-closures/

http://javascriptissexy.com/understand-javascript-closures-with-ease/

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
    
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain

http://stackoverflow.com/questions/3564238/object-oriented-javascript-with-prototypes-vs-closures


**[⬆ back to top](#table-of-contents)**


## Object

http://howtonode.org/what-is-this

https://javascriptweblog.wordpress.com/2010/08/30/understanding-javascripts-this/

http://stackoverflow.com/questions/3127429/how-does-the-this-keyword-work

http://stackoverflow.com/questions/17260603/object-literal-vs-constructorprototype

http://www.quirksmode.org/js/this.html

http://blog.kevinchisholm.com/javascript/difference-between-object-literal-and-instance-object/

http://stackoverflow.com/questions/8093057/javascript-inheritance-and-the-constructor-property

http://robdodson.me/javascript-design-patterns-singleton/

http://stackoverflow.com/questions/22401553/what-are-all-the-difference-between-function-and-constructor-function-in-javascr


**[⬆ back to top](#table-of-contents)**

## Pattern

Module patterns

http://www.addyosmani.com/resources/essentialjsdesignpatterns/book/

http://www.adequatelygood.com/JavaScript-Module-Pattern-In-Depth.html

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

**[⬆ back to top](#table-of-contents)**
