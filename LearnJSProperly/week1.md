Learn JS Properly
===

# Reset and relearn JS
## 1. Learn some HTML & CSS(done).
## 2. Make a simple Web Site
## 3. Read "Beginning JavaScript" Chapter 1
### What is JavaScript?
It's a "computer programming language"!!!!!  
It's an "interpreted language" rather than a "compiled language".  
Nothing to do with "Java" language.  

JavaScript runs in browser with interpreters.(it can also be used in other "Hosts".)  
But need to be careful with different browsers.  
Standards set by W3C  
(Some WEB working fondamental concepts. Like web server, HTTP, client, IP addresse, DNS...etc)  

### Why learn JS
- it's widely used and available.
- it's very versatile(polyvalant), can be used in many cases.

What can JavaScript do? Well......a lot!!!  

### Tools needed to JavaScript Development
- a text editor
- a browser

### The Scripts go to ...
Since major browsers use javascript as default script language. `<script>` tag (without `type`) is enough. However use of the `type` attribute is "mandatory" according to W3C standards.

Linking to an External JS file by adding :
```
<script type="text/javascript" src= "THE.js"></script>
```
Advantages of Linking!  
- code reuse. Also easyer for maintanence.
- make it "cacheable"!

### Here Comes the First Program
You can put `<script>` where ever you want in a file. But it's better make it inside the `<head>` or the `<body>`.  
It's also better to always specify the "type" attribute like:
```
<script type="text/javascript">
```
Then finally the first page with JavaScript:
```
<html>
    <body bgcolor="WHITE">
        <p>Paragraph 1</p>
        <script type="text/javascript">
            document.bgColor = "RED";
        </script>
    </body>
</html>
```
- `document` refers to the web page "document".
- `bgColor` sets the background color.
- `;` is used to indicate the end of a "statement".
- "parsing" = gramatical analysis = read through the code and execute them.

To learn the "parsing" of a web page:
```
<html>
<body bgcolor="WHITE">
    <p>Paragraph 1</p>
    <script type="text/javascript">
        //a comment for first script block.
        alert("First Script Block");
    </script>

    <p>Paragraph 2</p>
    <script type="text/javascript">
        document.bgColor = "RED";
        alert("Second Script Block");
    </script>
    
    <p>Paragraph 3</p>
</body>
</html>
```
(if it doesn't work it might be a probleme because of copying directly from pdf. Replace `"` by `"` to fix it.)  

- `//` is to use for comment.
- `alert()` is a function (function = pieces of JS code. It takes some information, processes it, and gives a result.) that "alert" or "inform" the user by displaying message box. The message to be dissplay is given in te "()" as *parameter*.
- the `alert()` function is a *modal*. It means that the *parsing* of the page stops (brought to a halt) when `alert()` function is used and doesn't restart until the user closes the box.
- Setting properties of the page: HTML = static (set it once, cant change it); JS = dynamic(can change it all the time.)  

**So the use of JavaScript is to add some sort of intelligence or logic to the page, or to add special effects.

### Some "Writtings" to the page
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<body >
    <p id="ResultsP"></p>
    <script type="text/javascript">
    // Script block 1
    document.getElementById('ResultsP').innerHTML = 'Hello World!';
    </script>
</body>
</html>
```
- first three lines are to set the page as "xhtml". Not that important.
- give an "id" to the `<p>` tag.
- get the element who's id is XXX and set the content to "Hello World!".
- the code **should be after** the paragraph that you want to set.

### and finally some "browser" problems!
Let your page be backward compatible? or just let it "degrade gracefully"?  
(degrade gracefully = the page gives alert or still looks "OK" with older browsers.)

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
\\b              | Backspace
\\f              | Form feed
\\n              | New line
\\r              | Carriage return
\\t              | Tab
\\'              | Single quote
\\"              | Double quote
\\\              | Backslash
\\xNN            | NN is a hexadecimal number that identifies a latin-1 special character
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
