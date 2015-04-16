# Codecademy.com - JavaScript Track
## 1. Getting started with Programming
### REAL BASIC
- type a string `"NAME"` and to know it's "length" using `"name".length`.
- basic math with `+`, `-`, `*`, `/`. 
- write some comments with `//`
- An "interactive" example : `confirm("Confirmation dialogue!");` (It pops up a confirmation box.)
- "Alert" user with `alert()`.(An alert box will pop up.)<<--better add this in.
- Ask user to input something : `prompt("What are you asking for?");`.(A box asking for input will pop up.).
- basic data types: "numbers", "strings", and "boolean".
- print out things in console by : `console.log()`
- print out data in web page document by :`document.write()` <<-- learned it from elsewhere.
- comparison operators: `>`, `<`, `<=`, `>=`, `===`, `!==`. (Careful, single `=` is for assignment of value, `==` or `===` is for comparison equal.)

### Basic logics
- `if` statement.

```
if(this){
    console.log("that");
} else {
    console.log("another thing");
}

```

If this then print that in console. Otherwise print another thing in console.
- other than `console.log()` we can use `prompt()` or `alert()` or `confirm()` to make it interactive.
- Some more math an the precedence.( All works like in the school.)
- The "modulo" symbol: `%` will return the **remainder** of X devided by Y: `X % Y`.
- function `substring()` extract part of the string. Ex: `"Jason HUANG".substring(2, 9)` will extract `"son HUA"` from the string.

### Variables
- Declaration:
```
var varName = data;
```

### A Tiny Game Project
- First ask for confirmation: `confirm("Realy want to play?');`
- Declear an "age" variable then assign to a "prompt()" function: `var age = prompt("What's your age?");`
- Some `if`...`else` to check user's age.
- `console.log` some story line.
- Declare an "userAnswer" variable, and asigne it to a `prompt()` to ask for user to input.
- use `if`...`else` to check for the "userAnswer". Print out different result for "yes" and others.
- Ask user to rate the app by 10 using `prompt()` function, and print out different result using `if`...`else`. 

## 2. Functions
### Introducint Functions
- "Function" is a series of instructions put together as a package, so that we can reuse it whenever we need it.
- syntax to declare a function:
```
var functionName = function(){
    ACTION;
};
```
also
```
function functionName(ARGUMENT){
    ACTION
};
```
to call this function use `functionName(ARGUMENT VALUE)`.
- 


