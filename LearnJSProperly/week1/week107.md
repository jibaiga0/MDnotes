Learn JS Properly
===

# Beginning JavaScript Chapter 4 Functions and Scope
## What will we learn:
- How to create a function.
- Identifing, creating and using globale and local variables (scope).
- Using function as a value.

## What is "function"?
- A block of code that performs a certain task.
- Some JavaScript built-in functions: `parseInt()`, `isNaN()`...etc.
- Some function returns data, some just perform an action.
- Some needs to have "parameter(s)", some not.

## Creating Own Functions
- syntax:
```
function funcName(funcParam1, funcParam2){
    ACTION;
    return RESULT;
}
```
- Use meaningful word to name you function.
- If the `return RESULT` line is not added, the function will return *undefined*.
- function needs to be called to "function", just put:
```
funcName(theParam1, theParam2);
```
- Make a `fahrToCent()` function, and use it in other part of code:  

```
function fahrToCent(degFahr){
    var degCent = 5 / 9 * (degFahr - 32);
    return degCent;
}
var degFahr = [prompt("First:"), prompt("Second:")];
var degCent = [];
var loopCounter = 0;

for(loopCounter = 0; loopCounter < 2; loopCounter += 1)
{
    degCent[loopCounter] = fahrToCent(degFahr[loopCounter]);
    console.log(degCent[loopCounter]);
    document.write(degCent[loopCounter]);
}
```
this will ask user to put in two numbers, convert them from Fahrentheigt to Centigrade, and then print them out both in console and web page document.
(the array [prompt("First:")......] is what I think of it my self, don't know if it's a good practice.)

## Scope and Lifetime
### Global Scope
- A variable declared **Outside** of any function.
- It can be used througout the script.
- Whenever you change the value of a "globale variable", no matter where you do it (inside or outside of a function), that value will change "globaly". Ex:
```
var degFhar = 12;
function convertToCent(){
    degFhar = 20;
    var degCent = 5 / 9 * (degFhar - 32);
    return degCent;
}
```
The value of "degFhar" will be changed to 20 everywhere.
- Usually it's better to avoid creating global variables, because it can be easily and intentionally changed.

### Functional Scope
- A variable declared **Inside** of a function.
- It can not be accessed outside of that function.
- The parameters in the function is also local. (function(PARAMETER))
- Take the example above, and change it to:
```
function convertToCent(degFhar) {
    var degCent = 5 / 9 * (degFhar -32);
    return degCent;
}
```
then "degFhar" and "degCent" will both be functional/local variables.
- the *lifetime* of these local variables end when the function finished, and their values are lost.

### Identifier Lookup
- An *identifier* is the name given to a variable or a function.
- Javascript engine will *lookup* for the names and try to process them.
- If variables with the same name were defined both in global an functional scope. JavaScript will first lookup in local scope and use it to execute the function. If it doesn't find the variable localy, it will try to lookup for it in a global scope.
```
var degCent =999;
function convertToCent(degFhar) {
    var degCent = 5 / 9 * (degFhar -32);
    return degCent;
}
```
- It's PERFECTLY valid to use the same identifier/name for global and local variables, but it's highly recommended **NOT TO DO** so.

## Function as Values
- Functions are *first-class* citizens in JavaScript. === **We can treat functions as any other type of value**.
- It can be asigne to a variable:
```
var fharToCentConverter = convertToCent;
// asigne "convertToCent()" function to a variable. Don't even need the parantheses.
```
and we can call this function in two ways: 
```
document.write(fharToCentConverter(212)); // 100
document.write(convertToCent(212)); //100
```
- It can be passed to another function's parameter:
```
function doSomething(fn){
    fn("Hey You!!");
}
doSomething(alert);
```
The `alert()` function will be pass into `doSomething()` function as parameter.  
My own ex:

```
function convertToCent(degFhar) {
    degFhar = prompt("Degree?");
    var degCent = 5 / 9 * (degFhar -32);
    return degCent;
}

function hotOrNot(fn) {
    if (fn < 20){
       return "So Cold! It's " + fn + " degree."; 
    } else if(fn <50) {
        return "HOT!!!!!It's " + fn + " degree.";
    } else {
        return "Are you kidding me?";
    }
}

document.write(hotOrNot(convertToCent()));
```
- Another example from the book:
```
function toCentigrade(degFahren) {
    var degCent = 5 / 9 * (degFahren - 32);
    document.write(degFahren + " Fahrenheit is " +
    degCent + " Celsius.<br/>");
}

function toFahrenheit(degCent) {
    var degFahren = 9 / 5 * degCent + 32;
    document.write(degCent + " Celsius is " +
    degFahren + " Fahrenheit.<br/>");
}

function convert(converter, temperature) {
    converter(temperature);
}

convert(toFahrenheit, 23);
convert(toCentigrade, 75);
```
First create two converter functions. Then create a convert calculator. Call them!!!!




