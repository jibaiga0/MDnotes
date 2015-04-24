Learn JS Properly
===

# Beginning JavaScript Chapter 3. Decisions and Loops
Make computer more intelligent by giving it decision-makeing abilitys.

## What we'll learn?
1. Number or string comparison.
2. Making decision with the `if`, `else`, and `switch`.(answer is ether *true* or *false*).  

## Comparison Operators
First get some "tools" in hand: operators (used between LHS (Left Hand Side) and RHS, normaly called "Left Operand" and "Right Operand".  

| Operator | Purpose
| ---      | ---
| ==       | equal to
| <        | less than
| >        | greater than
| <=       | less than or equal to
| >=       | greater than or equal to
| !=       | not equal to

order of "PRECEDENCE":  
`==` and `!=` are lowest, `>`, `<`, `<=`, `>=` and `!=` are all the same.  

**On [w3school:Javascript best practices](http://www.w3schools.com/js/js_best_practices.asp) and on [24 JavaScript best practices](http://code.tutsplus.com/tutorials/24-javascript-best-practices-for-beginners--net-5399), they suggested not to use `==` or `!=`, but use `===` and `!==`. Because `==` and `!=` automaticly convert the operand to compariable types, it may cause some problem sometimes.**  

The result of the comparison can be assign to a variable. (value will be either *true* or *false*.)  

## The *IF* Statement
Syntax will looks like:  
```
if(TEST CONDITION) {
    CODES
}
```
It's read like " `if` the `(TEST CONDITION)` is true, then run the `CODES`."  
`{ }` marks "block of code" in JavaScript.  

## Logical Operators

Operator     | Function
---          | ---
&&           | AND
&#124;&#124; | OR
!            | NOT

Logic!!!  

Multiple conditions can be pass in to `if()` statement. Ex:  
```
if(THIS && THAT ! THAT1) {
    ACTION;
}
```

One simple example:  
```
var myAge = parseInt(prompt("Your age?", ""), 10);
if (myAge >= 3 && myAge <=10){
    document.write("You are a child.");
}
if( (myAge <= 18 && myAge >=3) || (myAge >=70 && myAge <= 123) ) {
    document.write("Probably too old or too young");
}
```

## else and else if
syntax:  
```
if(CONDITION){
    ACTION1;
} else {
    ACTION2;
}
```
`if` the "CONDITION" is "true" do "ACTION1", or `else` do "ACTION2".

```
if(CONDITION1){
    ACTION1;
} else if (CONDITION2){
    ACTION2;
} else {
    ACTION3;
}
```

`if` the "CONDITION1" is "true" do "ACTION1, `else if` the "CONTITION2" is "true" do "ACTION2", `else` do "ACTION3".

## String Comparison
using same operators, but it compares all letters, and "case sensitive".  
It compares the ASCII Unicode number of each character.  
To get rid of case sensitive problem, just convert string operands to all uppercase or all lowercase by using:  
`toUpperCase()` or `toLowerCase()`.

## Switch
A more efficient to check for large number of possibility.  
syntax:  
```
switch(aVariable)
{
    case "Paul":
        ACTION1;
        ACTION2;
        break;

    case "Jason":
        ACTION3;
        break;

    default:
        ACTION0;
        break;
}
```
- Start a `switch()` function, pass in "aVariable" that we want to check.
- For the `case` of "Paul" do "ACTION1" then "ACTION2" then stop at the `break` point.
- For the `case` of "Jason" do "ACTION3" then stop.
- For all other cases(default case), do "ACTION0. (`default` statement is optional, but always good to declare it.)  

example is a number guessing script:

```
var theNumber = prompt("guess it's 1 or 2", "");
theNumber = parseInt(theNumber,10);

switch(theNumber) {
     case 0:
        alert("Too low!");
        break;
    
    case 1:
        alert("Too low!");
        break;

    case 2:
        alert("That's it!");
        break;

    default:
        alert("Please enter 1 or 2.")
        break;
}
```

- the "case 0" and "case 1" are doing the same thing so we can merge it like:  
```
    case0:
    case1:
        alert("Too low!");
        break;
```
- this will do the same thing for "case0" and "case1".

## Looping - FOR and WHILE
Repeat the same thing when condition matched.  
Using `for` and `while` statement.  

### for loop
- use the code a cetain number of times.  
Syntax:  
```
for(loopCounter = 1; loopCounter <= 3; loopCounter += 1)
{
    ACTION;
}
```
This code says: Initiate the "loopCounter" to be "1", when the "loopCounter" is less then or equal to "3", do the "ACTION" and add "1" to "loopCounter".
(number of *iteration*.)  

Converter example:

```
var degFahren = [212, 32, -459.15];
var degCent = [];
var loopCounter;

for (loopCounter = 0; loopCounter <= 2; loopCounter += 1) {
    degCent[loopCounter] = 5/9 * (degFahren[loopCounter] - 32);
}

for (loopCounter = 2; loopCounter >= 0; loopCounter -= 1) {
    alert("Value" + loopCounter + ":" + degFahren[loopCounter] + "°F");
    alert("Whitch is " + degCent[loopCounter] + "°C");
}
```
- First declare Variables.
- Loop through the array "degFahren", convert the value and sotre it into "degCent".
- Loop "BACK" and print out the values.

## The "for...in" Loop
Use it to loop throug all items in an **array** (without knowing the exact number of the items.)

syntax:

```
var arrayIndex;
for (arrayIndex in arrayName) {
    ACTION;
}
```
- "arrayIndex" is a variable which will automatically be populated with/assign to the next index value in the array.
- This code will loop through all items in the array "arrayName" and each time put the index number into "arrayIndex".  

Ex: (two ways to loop througe `var myArray = ["Paul", "Jason", "NOOB"];`)

```
var loopCount;
for (loopCount = 1; loopCount < 3; loopCount += 1){
    alert(myArray[loopCount]);
}
```
or

```
var loopCount;
for (loopCount in myArray) {
    alert(myArray[loopCount]);
}
```
It just became shorter and looks cleaner!

## The while Loop
The differences between `for` and `while`: 
- `for` used for looping a certain number of times, `while` enables you to test a condition and keep looping while it's true.  
- `for` : when you know how many times you need to loop. `while`: when you don't know.  
(BUT ACTUALLY I JUST CAN'T SEE ANY "TRUE" DIFFERENCE......)

syntax:
```
while (CONDITION) {
    ACTION;
}
```

It can also do the same work as `if` by writing:

```
while (loopCount < x){
    ACTION;
    loopCount += 1;
}
```

This will loop through the "ACTION" "x" times.  
If you forget to put `loopCount += 1;`, the code will be an *infinite loop*.  

## The do...while loop
syntax:  
```
do {
    ACTION;
} while (CONDITION);
```
Use this if you want to run the action first and check if the condition is true, if yes, loop through the action.  
But it's rarely used, so try to avoid it unless really necessary.

## *break* and *continue
`break` can be used in `switch` statement, but also can be used to left a `for` or `while` loop.

Example:
```
var theNumber;
var xTimes;
theNumber = prompt("enter your number", "");

for (xTimes = 1; xTimes <= theNumber || isNaN(theNumber) === true ; xTimes += 1) {
    if(isNaN(theNumber)) {
        theNumber = alert("Put in a NUMBER please","");
        break;
    }
    document.write(theNumber + "*" + xTimes + "=" + (theNumber * xTimes) + "<br>");
}
```
- In this example, the script will alert "Put in a NUMBER please" and `for` loop will be stoped if user did not put in a number.   

```
var theNumber;
    var xTimes;
    theNumber = prompt("enter your number", "");

    for (xTimes = 1; xTimes <= theNumber || isNaN(theNumber) === true ; xTimes += 1) {
          if(isNaN(theNumber)) {
              theNumber = prompt("Put in a NUMBER please","");
              continue;
          }
          document.write(theNumber + "*" + xTimes + "=" + (theNumber * xTimes) + "<br>");
      }
```
- This example makes the code more interactive by replace the `alert` by `prompt`, and change `break` to `continue`.

