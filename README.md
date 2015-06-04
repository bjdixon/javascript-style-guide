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

* Use lowerCamelCase for variables, attributes and function names
* Use UpperCamelCase for constructor functions
* Use UPPERCASE for constants
* Underscores don't belong in variable names except for ``` _this ```
* Use 1 ``` var ``` keyword per scope and 1 declaration per line
* Unassigned variables follow assignments
* Hoist your variable declarations manually
* When storing a reference to 'this' (to be used in a child scope) the convention is to store it as ``` _this ```

## Objects

Rules for objects

## Arrays

Rules for arrays

## Functions

Rules for functions

## Type Checking and Comparisons

Rules for type checking and comparisons

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

