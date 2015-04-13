Learn JS properly
===

## 4. Beginning Javascript Ch.2
### Data Types and Variables
Information/Data comes in all sorts of forms : numbers, text, dates, times...etc.  
1. Data types.
2. How to store data (variable).
3. How to manipulate and process the data.

### Types of Data
- Real world data like : numbers, texts...
- programing data like : object (will look deeper in Chapter 4.).

strongly typed language vs weekly typed language  
In JavaScript we don't need to specify type when dealing with data.  
But we still need to know about data types in case it wents wrong.  
And it also helps to use data effectively.  

### Most commonly used data types
- **Numerical Data**  
*integer* : whole numbers like 999, 7...  
*floating-point* : fractional numbers such as 3.1415...  
(they are used as is).

- **Text Data**  
*string* : one or more charaters of text.  
(it's marked by surrounded `"`.ex: `"Here are some texts."`)  
escape character `\` to print out special characters.  
Some examples:  

escape sequence | Character Represented
---             | ---
\\b             | Backspace
\\f             | Form feed
\\n             | New line
\\r             | Carriage return
\\t             | Tab
\\'             | Single quote
\\"             | Double quote
\\\             | Backslash
\\xNN           | NN is a hexadecimal number that identifies a latin-1 special character
For instance if you want to type a copyright symble ©, you will have to put `\xA9` into the JavaScript code.  
- **Boolean Data**  
Yes or No, positive or negative, true or false, 1 or 0.  
*true* for yes, *false* for no.  
(Boolen is named after its inventor George Boole!)
It is to give the program decision-making abilities.

### Variables - storing data in memory
- we want to store permanent datas in a *database*. And those temporary, altered, varied datas will be store in *variable*.
- the *variable* will be stored in the computer's memory, whitch is much much faster then in the *database*.
- variable nameing rules:  
1.It's case sensitive.  
2.Can't use *reserved* words : `var`, `with`...etc.  
3.Can't use certain characters : `&`, `%`...etc.  
4.Can't start with numbers : `99kids`, `101building`...etc. But numbers can appear in other places, such as : `kids99`, `building101`.

### Variable declaration and Value association
- declare a variable by writing:
```
var newVariable;
```
- assigne a value to it by doing:(the equal sign `=` is called an *assignment operator*)
```
newVariable = 999999;
```
- A real time example:
```
<!DOCTYPE html>
<html>
<head>
</head>
<body>
    <script type="text/javascript">
    var newVariable;
    alert(newVariable);

    newVariable = "Hey";
    alert(newVariable);

    newVariable = 987654321;
    alert(newVariable);
    </script>    
</body>
</html>
```
- since JS is weekly typed language, variable can switch type whenever you want it to be.
- note that when trying to alert the variable without assignment, it prints out *undefined*, whitch is a primitive value in JS. And it can be compared, such as checking if the variable is assigned or not.

### Assigning Variables with the value of other variables
- Not only can we assigne numbers or strings, but we can also assigne the value of other variables.ex:
```
var variable1;
var variable2;
variable1 = 390;
variable2 = variable1;
```

- A more complex example:  

```
var string1 = "this";
var string2 = "that";
alert(string1);
alert(string2);

string2 = string1;
alert(string1);
alert(string2);

string1 = "another";
alert(string1);
alert(string2);
```
(note that in the last block even the "string1" been reassigne to another value. the "string2" remains the same as it just copied the value from the former "string1" value. It's not always the case but generaly "basic data types" like numbers or strings are always copied when assigned. And for more complex data types like *object*, the value is shared.)  
ex:  
```
var string = "hello";
var string1 = string;
var string2 = string;
var string3 = string;
// changing any of the variable won't effect others.

var object = someFunction();
var object1 = object;
var object2 = object;
var object3 = object;
// changing any of the variale will effect all. Because they share the same function().
```
### Using Data - Calculations and String Manipulation
Why using variables?  
Store variables in memory, then calculate or processe it latter.  
Here we are going to talk about some "number-crunching" and "text operation" with variables.  

### Numerical Calculation
operators : addition `+`, subtraction `-`, multiplication `*`, division `/`.  
It's normaly better to put numbers into variables and do the calculation using variables.

**Increment and Decrement operators.**  
`++` for increment, `--` for decrement.  

```
var thisNum = 0;
thisNum = thisNum + 1;
thisNum++;
++thisNum;
```
Three lines give the same result(store 1 to "thisNum"), since the `++` operator is used alone.

BUT when `++` and `--` utilize with other operators, the placement becomes effective. Ex:

```
var thisNum = 1;
var thisVar = thisNum++ \* 20;
alert(thisVar);
alert(thisNum);
```
First do thisNum \* 20, store it to thisVar.  
Then do thisNum + 1, store it to thisNum.  
So the first alert gives 20, and the second alert gives 2.

```
var thisNum = 1;
thisVar = ++thisNum \* 20;
alert(thisVar);
alert(thisNum);
```
Frist do "thisNum" + 1 then \* 20, store the result to "thisVar".  
Also store "thisNum" + 1 to "thisNum".
So the first alert gives 40, and the second gives 2.
*VERY DIFFERENT HERE*

Some MORE complex example:
```
var thisNum = 1;
var thisVar = (thisNum++ \* 10 + 2);
// 1. "thisNum" \* 10 + 2 = 12, store it to "thisVar".
// 2. "thisNum" + 1 = 2, store it to "thisNum".
thisVar = (++thisNum \* 10 + 2);
// 1. ("thisNum" + 1) \* 10 + 2 = 22, store it to "thisVar".
// 2. "thisNum" + 1 = 2, store it to "thisNum".
```
*A HUGE ERROR at p.30 in the book. Where the author said the value of "thisNum" in the first two lines is going to be 12.*

*Actually with such subtlety, it can lead to bugs and security problems. So it's usually better to AVOID this syntax. so...*
> DON'T USE `++` AND `--` IN JAVASCRIPT.  

(also disscused in the YUI video of Crockford : Crockford on Javascript - part5 the end of all things. 1:09'00".)

The **GOOD** alternative would be `+ =` operator. It has 3 better resons:  
1.It also shortens/simplified the code.  
2.It can also apply to other calculation operators `-`, `*`, and `/`.  
3.It can operate numbers other then 1.
4.It makes no ambiguity.


## Codecademy.com - JavaScript Track
### Getting started with Programming
- type a string `"NAME"` and to know it's "length" using `"name".length`.
- basic math like `3 + 4`, `5 / 9`
- write some comments with `//`
- An "interactive" example : `confirm("Confirmation dialogue!");` (It pops up a confirmation box.)
- Ask user to input something : `prompt("What are you asking for?");`.(A box asking for input will pop up.).
- basic data types: numbers, strings, and boolean.
- print out things in console by : `console.log()`
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
---------No 19
