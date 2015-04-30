Learn JS properly
===

# Beginning JavaScript Chapter 5 - An Object-Based Language
## We Will Learn
- Using JavaScript's built-in object to work with complex data
- Creating custom objects.
- Defining custom reference types.

## What are objects? 
- A **car** *object* has a **color** *property* whitch has a **red** *value*. You can use it's *method*/*function* such as **ignition**, **beep the horn**,**changing gear**...etc. And sometimes you need to give a *parameter* to use it's *function* like 1, 2, 3, or, 4 to change the gear. Some *functions* may *return* values to the user, like the cold air from air conditionor.
- Before this point, we are dealing with *primitive* data. Actual data whitch is not complex.
- When do we need to use *object*? Take time calculation for example. If we do it in traditional math calculation, it's going to be complicated to handle the 24 hours a day, 60 minutes an hour values. So the `Date` object comes in handy!

## Creating an Object
- To create an object: `var theVariable = new objectConstructor();`
- Unlike **primitive** data(numbers, strings...etc), if we assign an object to a variable, it will just be a refrence to it. So the variable doesn't have it's own copy of the object. Ex:

```
var myObject = { "name" : "JJ"};
var myObjRef = myObject;
myObject.name = "KK";
alert(myObjRef.name); // Will print out KK.

var myString = "JJ";
var myStr2 = myString;
myString = "KK";
alert(myStr2); // Will print out JJ.
```

## Object's Properties and methods
- Use the properties: `myObject.propertyName`.
- Use the methods: `myObject.methodName()`.( Should use `()`.)

## Primitive *Objects*
- Actually primitive data can also be seen as object , and they have their own properties and methods.
- To create a *String* object: `var myString = new String("This is a string");`. (But normaly we only do:`var myString = "This is a string";`)
- To use the *length* property of a string: `var stringLenght = myString.length;`.

## Native Object Types
### String Objects
Create it using *litteral* expression:`var myString = "Hello";` (It's the better way!).

1. **length** (property)  
It simply returns the number of characters in a string.
2. **indexOf()** and **lastIndexOf()** (method)  
Use to search for the occurrence of one string inside another, and return it's index number.  
They can take two parameters: The string to find. The position to start the search(optional, starts at 0 if not specified.).  
`indexOf()` will search from the begning, while `lastIndexOf()` will search from the end.  
```
var myPhrase = "Tell me your secret. Your top secret.";
var whereSecret = myPhrase.indexOf("secret");
alert(whereSecret); // find the first "secret" and return 13.
var lastSecret = myPhrase.lastIndexOf("secret");
alert(lastSecret); // find the last "secret" and return 30.(it counts from the begning.)
```   
These methods are more useful when coupled with `substr()` and `substring()` methods.
3. **substr()** and **substring()** (method)  
Copy part of a String. They both take 2 parameters, the first one set the starting index. The second ones are slightly different, for `substr()`, it's the *length* of the string desiered, for `substring()` it's the *index* after the last caracter desiered. (`substr()` is more used today!) Ex: (Add on to the codes above.)  
```
var mySubStr = myPhrase.substr(whereSecret, 6);
alert(mySubStr);
```  
4. **toLowerCase()** and **toUpperCase()** (method)  
Converting Case. Takes no parameters(But still need to put `()` since it's a *method*. Ex:   
```
var myString = "WoRdS";
alert(myString.toLowerCase()); // this will alert "words".
```
5. **charAt()** and **charCodeAt()** (method)  
Select single character in a string. And it's useful to check validity of user input. It takes one parameter: The index number of the charater you're looking for. And it returns that character.  
```
// Print out the last character of the user input.
var yourString = prompt("Enter something:");
var lastChar = yourString.charAt(yourString.length - 1);
alert(lastChar);
// check the last character's case.
var charCase = "Not a character or a number.";
var charCode = lastChar.charCodeAt(0);
if (charCode >= "A".charCodeAt(0) && charCode <= "Z".charCodeAt(0)) {
    charCase = "Upper case character.";
} else if (charCode >= "a".charCodeAt(0) && charCode <= "z".charCodeAt(0)) {
    charCase = "Lower case character.";
} else if (charCode >= "0".charCodeAt(0) && charCode <= "9".charCodeAt(0)) {
    charCase = "Number!";
} else {
}
alert(charCase);
```
6. **fromCharCode()** (method)  
Can be seen as the opposite of `charCodeAt()`. It's a *static* method, means that it can be called without creating a string object. Ex: `var alphaBeta = String.fromCharCode(65, 66)` this will assign "AB" to the variable "alphaBeta".
7. **trim()** (method)  
Remove leading and trailing whitespace. Normally used to "trim" user input (usually we don't want any whitespace leading or trailing).  
It takes no parameter???  
```
var userInput = prompt("Type something");
var stringTrimed = userInput.trim();
alert(stringTrimed);
// So if the user type in "       JJ    ", the string will be trimed to "JJ".
```

### Array Objects
1. **length** (property)  
Find out number of elements.  
```
var myArray = [12, 34, "JJ"];
var arrayLength = myArray.length;
alert(arrayLength);
```
2. **push()** (method)  
To add elements. Put the element to add as parameters.
```
var myArray = [12, 34];
myArray.push("JJ");
alert(myArray);
```
3. **concat()** (method)  
To join arrays.  Take the array to be added as parameters.
```
var array1 = [12, 34];
var array2 = [56, 78];
var join1 = array1.concat(array2);
alert(join1); // array will be 12, 34, 56, 78
var join2 = array2.concat(array1);
alert(join2); // array will be 56, 78, 12, 34
```
4. **slice()** (method)  
Copying part of an array. Take two numbers as parameters, starting index and ending index.
```
var myArray = [12, 34, 56];
var shortArray = myArray.slice(0,2);
// the shortArray will be [12, 34].
```
5. **join()** (method)  
Convert array to a single string. Takes one parameter, and use it as the characters to be added between array elements.  
```
var myArray = [12, 34, 56];
var arrayString = myArray.join(" ");
// arrayString will be: "12 34 56"
```
6. **sort()** (method)
Put the array in order. Elements are sorted by the unicode number.
```
var myArray = [34, 56, 12, "DEF", "def", "abc", "ABC"];
myArray.sort();
// myArray will then be [12, 34, 56, "ABC", "DEF", "abc", "def"];
```
7. **reverse()** (method)  
Putting array in reverse order (of the current order).  
```
var myArray = [34, 56, 12, "DEF", "def", "abc", "ABC"];
myArray.reverse();
// makes the array become ["ABC", "abc", "def", "DEF", 12, 56, 34]
```
8. **indexOf()** and **lastIndexOf()** (method)  


