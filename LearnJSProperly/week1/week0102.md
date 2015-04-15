Learn JS Properly
===

# 4. Beginning Javascript Ch.2
## Data Types and Variables
Information/Data comes in all sorts of forms : numbers, text, dates, times...etc.  
1. Data types.
2. How to store data (variable).
3. How to manipulate and process the data.

## Types of Data
- Real world data like : numbers, texts...
- programing data like : object (will look deeper in Chapter 4.).

strongly typed language vs weekly typed language  
In JavaScript we don't need to specify type when dealing with data.  
But we still need to know about data types in case it wents wrong.  
And it also helps to use data effectively.  

## Most commonly used data types
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

## Variables - storing data in memory
- we want to store permanent datas in a *database*. And those temporary, altered, varied datas will be store in *variable*.
- the *variable* will be stored in the computer's memory, whitch is much much faster then in the *database*.
- variable nameing rules:  
1.It's case sensitive.  
2.Can't use *reserved* words : `var`, `with`...etc.  
3.Can't use certain characters : `&`, `%`...etc.  
4.Can't start with numbers : `99kids`, `101building`...etc. But numbers can appear in other places, such as : `kids99`, `building101`.

## Variable declaration and Value association
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

## Assigning Variables with the value of other variables
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
## Using Data - Calculations and String Manipulation
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

A good alternative for `++` or `--` is to use `+=` operator. Resons that it's better:  
1. Simple behavior makes no ambiguity.
2. Can be used not only for `+` and `-`, but also for `*`, and `/`. Ex: 
```
var thisNum * = 20;
// means thisNum = thisNum * 20;
```
3. Can be used to other numbers then "1".

The "operator precedence" works as in mathmatics. First `*` `/` then `+` `-`.

**Try to make an "EURO to NTD" converter.**  

Using `prompt()` function to get data from user input. It's like an `alert()` with an input box.  
`prompt()` function can take two arguments in respective order: 
1. Text to be displayed.
2. The default value contained in the input box.

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>EURO to NTD</title>
</head>
<body>
    <script type="text/javascript">
        // A simple EURO to NTD converter.
        var exRate = prompt("Exchange rate is:", 35);
        var amountEuro = prompt("Amount in Euro:", 1000);
        var exEuroToNtd;

        exEuroToNtd = exRate * amountEuro;
        alert(exEuroToNtd);
    </script>
</body>
</html>
```

And a "BMI Calculator"!!
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>BMI Calculator</title>
</head>
<body>
    <script type="text/javascript">
        // BMI = weihght(kg) / (height(m) * height(m)).
        var yourWeight = prompt("Your weight is (in KG):", 55);
        var yourHeight = prompt("Your height is (in m):", 1.7);
        var yourBMI;

        yourBMI = yourWeight / (yourHeight * yourHeight);
        alert(yourBMI);
        if(yourBMI > 25) {
            alert("You are overweight!");
        } else if(yourBMI < 18){
            alert("You are underweight!");
        } else {
            alert("You have a nice body!!!");
        }
    </script>
</body>
</html>
```
**No checking of data input here, so you can enter whatever you want, such as "abc" instead of numbers. We will learn about data validation latter.**

### Basic String Operations - Concatenation  
Join two strings to make one string by using `+` operator.
```
var myFullName = "Jibai"+ " " + "Gao";
```

(Mush put a white space in it or it will print out "JibaiGao", instead of "Jibai Gao".)  
Another simple Web Page example:  
```
<!DOCTYPE html>
<html >
<head>
    <meta charset="UTF-8">
    <title>concatenation example</title>
</head>
<body>
    <script>
        var yourFirstN = prompt("Your first name:");
        var yourLastN = prompt("Your last name:");
        var yourFullN = yourFirstN + " " + yourLastN;
        var greetingString = "Hello";
        var concatString;
        
        document.write(greetingString + " " + yourFullN + "!" + "<br>");

        concatString = greetingString + " " + yourFullN + "!";

        document.write(concatString);

    </script>    
</body>
</html>
```
This above is some concatenation example and how to use `document.write()` function to write data into (html) document.  

### Mixing Numbers and Strings
Just use `+` to add them together.  
When Numbers mix with Strings, JS will just convert the numbers into strings and make a "string concatenation".   

Write following line in the "BMI Calculator" to make it clearer and more user friendly.
```
document.write("Your BMI = " + yourWeight + " / " + yourHeight + "\xB2 = " +  yourBMI);
```
This will print out (with default values) "Your BMI = 55 / 1.7² = 19.031141868512112" on the web page.  

(Will learn more in depth in Chapter 5 and 6.)  

## Data Type Conversion
It's important since numbers, strings and mix of both are behaved differently.  
`"22" + "11"` result in 2211(treated like strings),  `22 + 11` result in 33(as numbers).  
Some interesting behavior here:  
`1 + 2 + "abc"` will give `3abc`.  
`"abc" + 1 + 2` will give `abc12`.  
`"abc" + 1 / 2` will give `abc0.5`.  
`"abc" + 1 - 2` will give a `NaN`(Not a Number).

Two conversion fuctions to convert strings to numbers: `parseInt()` and `parseFloat()`.  
Why the name "parse" rather then "convertTo"? Because it just "parse"(analize/ goes through...) the argument given, check if it's a valid number, then build the number that it gets or just stop the work.  
Ex: `parseInt("123")` this will give 123 as a number.  
`parseInt("123abc")` also gives number 123.  
`parseInt("123abc456") it takes only the first numerical part of the string. So it gives number 123 too.  
Note that if you put a real "string" as argument(or the argument start's with strings), it will give "NaN", as result.  

Example:  
```
var theString = "59.98 degrees";
var thisInt;
var thisFloat;

thisInt = parseInt(theString, 10);
alert(theString + " converted to Intenger　” + thisInt + "<br/>")

thisFloat = parseFloat(theString);
alert(theString + " converted to Float " + thisFloat)
```

The 10 in the `parseInt()` function is called **radix**, it tells `parseInt()` to convert the number in decimal base. (2 for binary, 16 for hex...etc)  
Ex: `parseInt(10, 2)` === 101.
**SHOULD ALWAYS USE THE RADIX!!**  
`parseInt()` only prints out 59  
`parseFloat()` prints out 59.98  
If passed in a "pure" string as argument , it gives "NaN".  
Nan is also a NUMBER, and it has it's own function `isNaN()`. It's used to check if the data is "NaN".  
Ex: `thisThing = isNaN("hello");` then "thisThing = true". It's useful to varify user inputs.

## Arrays
- Normal variable take only one value. An array can store more then one value.
- The order starts at "0". Not "1".
- To declare an array: `var thisArray = new Array();` (this is no more a good practice, now we do: `var thisArray=[];`.
- Two ways to pass data into array:  
1.
```
var thisArray = ["jkl", 456, 908, "yes"];
```
The value of thisArray[0] will be "jkl", thisArray[2] will be "908".  
2.
```
var thisArray = [];
thisArray[0] = "jkl";
thisArray[1] = 456;
thisArray[2] = 908;
thisArray[3] = "yes";
```
This gives the same result as 1.
- normaly 1st method is used to create and array if we already know what to put in. And the 2nd way is used if we dont know yet what to put in the array or we want to change a specific item inside an array.  
- When useing the 2nd way, items added dont need to be in order. We can also do:  
```
var thisArray = [];
thisArray[999] = "nine nine nine";
thisArray[100] = 123;
```
Other items in the array will be "undefined".  

### Multi Dimensional Array
- Two dimensional array:  

```
var twoDArray = [];

twoDArray[0] = [];
twoDArray[0][0] = "name1";
twoDarray[0][1] = "age1";

twoDArray[1] = [];
twoDArray[1][0] = "name2";
```
- It can have more dimentions follow the same syntax, but dont try to do to much!  
