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
### Introducing Functions
- "Function" is a series of instructions put together as a package, so that we can reuse it whenever we need it.
- syntax to declare a function:
```
var functionName = function(ARGUMENT){
    ACTION;
};
```
also
```
function functionName(ARGUMENT){
    ACTION
};
```
But it's better to always use the first method.(declare the var first!!).  
to call this function use `functionName(ARGUMENT VALUE)`.  
One brief example:
```
var calculate = function (number) {
    var val = number * 10;
    console.log(val);
}
calculate(20);
```
- make it `return` a value:
```
function timesTwo(number){
    return number * 2;
}
//and then call it
var calculatedNum = timesTwo(20);
console.log(calculatedNum);
```
- Combine with `if`...`else` statement:  

```  
function quarter(number){
    return number/4;
}

var theNumber = prompt("put in a number", " ");
if (quarter(theNumber) % 3 === 0){
    console.log("TRUE");
} else {
    console.log("FALSE");
}
```  
- A function can take TWO (or more?) parameters. Ex: `function thisFunc(X, Y) { ACTION }`

### SCOPE
- "Global" vs "Local" variables.  
"Outside" vs "Inside" of the function.

### Build "Rock, Paper, Scissors"
- First ask for user's choice:  
```
var userChoice = prompt("Do you choose rock, paper or scissors?");
```
- Then mak computer chose randomly with `Math.random()`:
```
var computerChoice = Math.random();
if (computerChoice < 0.34) {
	computerChoice = "rock";
} else if(computerChoice <= 0.67) {
	computerChoice = "paper";
} else {
	computerChoice = "scissors";
}
```
- Make the `compare()` function and it's logic:
```
function compare(choice1, choice2) {
    if (choice1 === choice2) {
        return "The result is a tie!";
    } else if (choice1 === "rock") {
        if (choice2 === "scissors"){
            return "rock wins";
        } else {
            return "paper wins";
        }
    } else if (choice1 === "paper") {
        if (choice2 === "rock") {
            return "paper wins";
        } else {
            return "scissors wins";
        }
    } else if (choice1 === "scissors") {
        if (choice2 === "paper") {
            return "scissors wins";
        } else {
            return "rock wins";
        }
    }
}
```
- Finaly call the function `compare()` with `userChoice, computerChoice` as parameters:
```
compare(userChoice, computerChoice);
```

Think about some problems:
1. How to varify if user puts in a valid choice?
2. How to add another choice?
3. How to ask players to rechose again when tied instead of just print out the result?
