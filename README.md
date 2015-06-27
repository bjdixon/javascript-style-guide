# JavaScript Style Guide

One small step towards clean code is the use of a style guide. Almost any style guide will do as long as the whole team uses it. The goal being that all code in the teams repo looks like it was written by a single person. Consistency is key.

## Contents

* [Formatting](#formatting)
* [Variables](#variables)
* [Objects](#objects)
* [Arrays](#arrays)
* [Functions](#functions)
* [Type Checking and Comparisons](#type-checking-and-comparisons)
* [References and Further Reading](#references-and-further-reading)

## Formatting 

Rules for whitespace, indentation, blocks, quotes and comments

### Whitespace

* Use spaces not tabs
* Eliminate end of line whitespace
* Eliminate empty line whitespace
* A maximum of 1 blank line separates code blocks
* Do not insert a blank line between a comment and the code block that it describes
* Precede a curly brace with a space
* Commas should be followed by a space or new line
* Don't add space following opening parentheses or preceding closing parentheses
* Add a single space following opening curly braces and preceding closing curly braces unless curly braces are empty
* Add a single space following the semicolons in the conditions of a for loop
* Add a single space after the keyword ``` function ```
* Separate operators and operands with a whitespace

### Indentation

* All Javascript code is indented by 2 spaces (tabs should be set in your editor to expand to 2 spaces)
* Code blocks should be indented (always indent code within curly braces)
* Indent function chaining and multiple variable declarations

### Beautiful Syntax

* Never use one line if/else/for/white/try/function statements
* Always use braces with if/else/for/white/try statements
* Use whitespace to promote readability 
* Always use single quotes except for JSON
* Never exceed a maximum of 100 characters per line
* Use slashes for comments, including multiline comments

## Variables

Rules for naming and how to declare variables

* Use lowerCamelCase for variables, attributes and function names
* Use UpperCamelCase for constructor functions
* Use UPPERCASE for constants
* Underscores don't belong in variable names except for ``` _this ```
* Use 1 ``` var ``` keyword per scope and 1 declaration per line
  ```
  var foo = 'bar',
    num = 1;
  ```
* Unassigned variables follow assignments
  ```
  var foo = 'bar',
    num = '1',
    undef;
  ```
* Hoist your variable declarations manually
  ```
  // Do this
  function good() {
    var bar;
    // statements
  }

  // Don't do this
  function bad() {
    // statements
    var bar;
  }
  ```
* When storing a reference to 'this' (to be used in a child scope) the convention is to store it as ``` _this ```

## Objects

Rules for creating and using objects

### Object Creation

* Use object literal syntax for creating objects not the constructor
  ```
  // Do this
  var item = {};

  // Don't do this
  var item = new Object();
  ```
* Use one line per property when creating objects
  ```
  // Do this
  var item = {
    propertyOne: 'value',
    propertyTwo: true
  };

  // Don't do this
  var item = { propertyOne: 'value', propertyTwo: true };
  ```
* Objects that are created with only one property may be created on one line
  ```
  // This is okay
  var item = { propertyOne: 'value' };
  ```

### Keys

* Don't use reserved keywords as keys
  ```
  // Don't do this
  var item = {
    default: { foo: 'value' },
    private: true
  };

  // Do this
  var item = {
    auto: { foo: 'value' },
    hidden: true
  };
  ```
* Use readable synonyms in place of reserved words, not alternative spellings of reserved words
  ```
  // Don't do this
  var item = { class: 'category' };

  // Don't do this either
  var item = { klass: 'category' };

  // Do this instead
  var item = { type: 'category' };
  ```

### Accessing Properties

* Use dot notation when accessing properties
  ```
  var item = {
    foo: 'bar',
    hidden: true
  };

  // Do this
  var foo = item.foo;

  // Don't do this
  var isHidden = item.['hidden'];
  ```
* Use subscript notation only when accessing properties using a variable 
  ```
  var item = {
    foo: 'bar',
    hidden: true
  };

  function getProperty(property) {
    return item[property];
  }

  var foo = getProperty('foo'),
    isHidden = getProperty('hidden');
  ```

## Arrays

Rules for creating and using arrays

* Use array literal syntax for creating arrays not the constructor
  ```
  // Do this
  var collection = [];

  // Don't do this
  var collection = new Array();
  ```
* Use ``` array.push ``` to add items to an array instead of direct assignment
  ```
  var collection = [];

  // Do this
  collection.push('value');

  // Don't do this
  collection[collection.length] = 'value';
  ```
* Use ``` array.slice ``` to copy an array
  ```
  var copyOfCollection = [],
    index;

  // Do this
  copyOfCollection = collection.slice();

  // Don't do this
  for (index = 0; index < collection.length; index += 1) {
    copyOfCollection[index] = collection[index];
  }
  ```
* Use ``` Array.prototype.slice ``` to convert an array-like object to an array
  ```
  function f() {
    var args = Array.prototype.slice.call(arguments);
  }
  ```

## Functions

Rules for declaring and invoking functions

### Function Declarations

* Always add a space after the ``` function ``` keyword
* Never declare a function in a non-function block (if, while, etc)
  ```
  // Don't do this
  if (somethingTrue) {
    function logTrue() {
      console.log(true);
    }
    logTrue();
  }
  ```

### Function Expressions

* Hoist declarations with other ``` var ``` declarations, but don't assign until after the other variables are declared
  ```
  var foo = 'bar',
    baz = true,
    multiply;

  multiply = function multiply(a, b) {
    return a * b;
  };
  ```
* Assigning the function to the variable at the site of first usage is prefered
* Providing an identifier is prefered as it allows for recursion and better stack traces
  ```
  // Prefer this
  var square = function square(number) {
    return number * number;
  };

  // Over this
  var anonymous = function () {
    return true;
  };
  ```
* Never declare a function in a non-function block. Assign the function to a variable instead. Browsers will allow you to do it, but they all interpret it differently
  ```
  // Don't do this
  if (somethingTrue) {
    function goTrue() {
      console.log(true);
    }
  }

  // Do this if you have to
  var goTrue;
  if (somethingTrue) {
    goTrue = function goTrue() {
      console.log(true);
    };
  }
  ```

### Constructor Functions

* Provide padding inside the braces when providing a configuration object during instantiation
  ```
  // Declaration
  function FooBar(options) {
    this.options = options;
  }

  // Usage
  var fooBar = new FooBar({ a: 'alpha' });

  // Usage with configuration object that has multiple properties
  var fooBar = new FooBar({
    a: 'alpha',
    b: 'beta'
  });
  ```

### Parameters and Arguments

* Never add padding inside parentheses
  ```
  // Do this
  function foo(paramOne, paramTwo) {
    // statements
  }
  
  foo(1, 2);

  // Don't do this
  function bar( paramOne, paramTwo ) {
    // statements
  }

  foo( 1, 2 );
  ```
* Always add a space after the comma following a parameter or argument
* Never name a parameter arguments. This will take precedence over the arguments object that is given to every function scope

### Write Small Functions

* Keep your functions short. A good function fits on a slide that people in the last row of a big room can comfortably read
* Prefer functions that are less than 25 lines of code
* Write functions that perform a single task

### Return Early From Functions

* Avoid deep nesting of ``` if ``` statements
* Always return a function's value as early as possible

```
// This is fine
function isPercentage(val) {
  if (val < 0) {
    return false;
  }
  if (val > 100) {
    return false;
  }
  return true;
}
 
// This is bad
function isPercentage(val) {
  if (val >= 0) {
    if (val <= 100) {
      return true;
    } else {
      return false;
    } 
  } else {
    return false;
  }
}
```

### Closures

* Don't use closures if you can use an inner function without a closure. They're slower and more prone to memory leaks
  ```
  function setupAlertTimeout() {
    var msg = 'Message to alert';
    window.setTimeout(function alertMsg() { 
      alert(msg); 
    }, 100);
  }

  // is slower than

  function setupAlertTimeout() {
    window.setTimeout(function alertMsg() {
      var msg = 'Message to alert';
      alert(msg);
    }, 100);
  }

  // which is slower than

  function alertMsg() {
    var msg = 'Message to alert';
    alert(msg);
  }
  function setupAlertTimeout() {
    window.setTimeout(alertMsg, 100);
  }
  ```
* Name your closures for better stack traces
  ```
  // Prefer this
  req.on('end', function onEnd() {
    console.log('good');
  });
 
  // Over this
  req.on('end', function () {
    console.log('bad');
  });
  ```
* Never nest closures. It's messy
  ```
  // Do this
  setTimeout(function connect() {
    client.connect(afterConnect);
  }, 1000);
 
  function afterConnect() {
    console.log('good');
  }
 
  // Don't do this
  setTimeout(function connect() {
    client.connect(function afterConnect() {
      console.log('bad');
    });
  }, 1000);
  ```

## Type Checking and Comparisons

Rules for comparisons and conditional evaluation

### Comparison Operators and Equality

**Prefer** ``` === ``` and ``` !== ``` **over** ``` == ``` and ``` != ```

Conditional statements evaluate their expression using coercion and always follow these rules:

* Objects evaluate to true
* Undefined evaluates to false
* Null evaluates to false
* Booleans evaluate to the value of the boolean
* Numbers evaluate to false if +0, -0, or NaN, otherwise true
* Strings evaluate to false if an empty string, otherwise true
* Arrays are objects and so evaluate as true

```
if ([0]) {
  // Arrays are objects and so evaluate as true
}
```

### Conditional Evaluation

**Strings**

```
// Do this when checking a string isn't empty
if (name) {
  // statements
}

// Don't do this
if (name !== '') {
  // statements
}

// Do this when checking a string is empty
if (!name) {
  // statements
}

// Don't do this
if (name === '') {
  // statements
}
```

**Collections**

```
// Do this when evaluating that an array has length
if (collection.length) {
  // statements
}

// Don't do this
if (collection.length > 0) {
  // statements
}

// Do this when evaluating that an array is empty
if (!collections.length) {
  // statements
}

// Don't do this
if (collection.length === 0) {
  // statements
}
```

**References**

```
// Do this when evaluating if a reference is false
if (!foo) {
  // statements
}

// Don't do this
if (foo === false) {
  // statements
}

// If checking a boolean is false as opposed to 0, undefined, NaN, '', or null
if (foo === false) {
  // statements
}

// When evaluating for null or undefined do this
if (foo == null) {
  // statements
}

// Don't do this (it's the same as above)
if (foo === null || foo === undefined) {
  // statements
}
```

### Checking for Types

* String ``` typeof foo === 'string' ```
* Number ``` typeof foo === 'number' ```
* Boolean ``` typeof foo === 'boolean' ```
* Object ``` typeof foo === 'object' ```
* Null ``` typeof foo === null ```
* Global undefined ``` typeof foo === 'undefined' ```
* Local undefined ``` typeof foo === undefined ```
* Null or undefined ``` typeof foo == null ```
* Array ``` Array.isArray(foo) ```

## References and Further Reading

The following lists of links were useful and borrowed from extensively in creating this style guide.

### Style Guide References

* [Idiomatic Style Guide](http://github.com/rwaldron/idiomatic.js)
* [Node Style Guide](http://github.com/felixge/node-style-guide)
* [Airbnb Style Guide](http://github.com/airbnb/javascript/tree/master/es5)
* [Crockford Style Guide](http://javascript.crockford.com/code.html)
* [JQuery Style Guide](http://contribute.jquery.org/style-guide/js/)

### Recommended further reading

* [ECMAScript 5.1](http://es5.github.com/)
* [Eloquent Javascript](http://eloquentjavascript.net/)
* [Adventures in Javascript Development](http://rmurphey.com/)
* [Perfection Kills](http://perfectionkills.com/)
* [Douglas Crockford](http://javascript.crockford.com/)

