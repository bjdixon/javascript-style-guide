# JavaScript Style Guide

Introduction, what this is and why it exists.

## Contents

* [Formatting](#Formatting)
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
* Use single quotes except for JSON
* Maximum of 100 characters per line
* Use slashes for comments, including multiline comments

## Variables

Rules for naming and how to declare variables

* Use lowerCamelCase for variables, attributes and function names
* Use UpperCamelCase for constructor functions
* Use UPPERCASE for constants
* Underscores don't belong in variable names except for ``` _this ```
* Use 1 ``` var ``` keyword per scope and 1 declaration per line
* Unassigned variables follow assignments
* Hoist your variable declarations manually
* When storing a reference to 'this' (to be used in a child scope) the convention is to store it as ``` _this ```

## Objects

Rules for creating and using objects

### Object Creation

* Use object literal syntax for creating objects not the constructor
* Use one line per property when creating objects
* Objects that are created with only one property may be created on one line

### Keys

* Don't use reserved keywords as keys
* Use readable synonyms in place of reserved words, not alternative spellings of reserved words

### Accessing Properties

* Use dot notation when accessing properties
* Use subscript notation only when accessing properties using a variable 

## Arrays

Rules for creating and using arrays

* Use array literal syntax for creating arrays not the constructor
* Use ``` array.push ``` to add items to an array instead of direct assignment
* Use ``` array.slice ``` to copy an array
* Use ``` Array.prototype.slice ``` to convert an array-like object to an array

## Functions

Rules for declaring and invoking functions

### Function Declarations

* Always add a space after the ``` function ``` keyword
* Never declare a function in a non-function block (if, while, etc)

### Function Expressions

* Hoist declarations with other ``` var ``` declarations, but don't assign until after the other variables are declared
* Assigning the function to the variable at the site of first usage is prefered
* Providing an identifier is prefered as it allows for recursion and better stack traces
* Never declare a function in a non-function block. Assign the function to a variable instead. Browsers will allow you to do it, but they all interpret it differently

### Constructor Functions

* Provide padding inside the braces when providing a configuration object during instantiation

### Parameters and Arguments

* Never add padding inside parentheses
* Always add a space after the comma following a parameter or argument
* Never name a parameter arguments. This will take precedence over the arguments object that is given to every function scope

### Write Small Functions

* Keep your functions short. A good function fits on a slide that people in the last row of a big room can comfortably read
* Prefer functions that are less than 25 lines of code
* Write functions that only perform one task

### Return Early From Functions

* Avoid deep nesting of ``` if ``` statements
* Always return a function's value as early as possible

### Closures

* Don't use closures if you can use an inner function without a closure. They're slower and more prone to memory leaks
* Name your closures for better stack traces
* Never nest closures. It's messy

## Type Checking and Comparisons

Rules for comparisons and conditional evaluation

### Comparison Operators and Equality

* Prefer ``` === ``` and ``` !== ``` over ``` == ``` and ``` != ```

Conditional statements evaluate their expression using coercion and always follow these rules:

* Objects evaluate to true
* Undefined evaluates to false
* Null evaluates to false
* Booleans evaluate to the value of the boolean
* Numbers evaluate to false if +0, -0, or NaN, otherwise true
* Strings evaluate to false if an empty string, otherwise true

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

