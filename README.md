# Javascript
Understanding Javascript better

## Table of Contents
1. [Functions](#Functions)

### Functions
- [1.1](#1.1) <a name='1.1'></a> **Difference between Functions Expression and Declaration**: 
```javascript
  // The named function expression is parsed from the start
  var functionName = function() {}
  // The function declaration is defined at run-time
  function functionName() {}
```

- [1.2](#1.2) <a name='1.2'></a> **Difference between Constructor Function and Object**:
```javascript
  var constructor = function(){
      this.firstMethod = function(){
         //something
      };
      this.secondMethod = function(){
         //something
      };
  };
  
  var object = {
    firstKey: function(){
       //something
    },
    secondKey: function(){
       //something
    }
};
```
