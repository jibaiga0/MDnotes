Learn JS properly
===

# Codecademy JavaScript track
# Data Structures - Arrays and Objects
## Array : review and more
- Create an array as always.
- Access an element inside an array by offset.(with the `[]` notation). Ex: `myArray[4]` for the 5th element in myArray.
- *Property* like `.length`.  The `.length` property in an array stores the number of elements in an array.
- Use `for` loop to loop through the array:
```
var languages = ["HTML", "CSS", "JavaScript", "Python", "Ruby"];
var loopCounter = 0;
for(loopCounter = 0; loopCounter < languages.length; loopCounter += 1){
    console.log(languages[loopCounter]);
};
```
- Heterogeneous arrays. We can put different types of data inside an array. Ex: `var mixArray = ["Super String", 999, veryFunc, true];` (the first one is a *string*, 2nd one is a *number*, 3rd one is a *function*(or *object*), 4th one is a *boolean* value.)
- Can put arrays inside an array. 2D array : `var arrArray = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];`
- You can also do *JAGGED*(鋸齒) arrays : `var jarrArray = [[1,2], [3, 4, 5], [6, 7]];`. And also array inside array inside array..... for multi demention arrays.

## Object : Put Nouns and Verbs together
- Nouns : numbers, strings, variables...; Verbs: functions...
- We can put them all inside an **OBJECT**. It's a collection of informations.
- Syntax:(Two ways to create object)
Object literal notation:
```
var myObject = {
    key1: valueA,
    key2: valueB,
};
```
Object constructor:
```
var myObject = new Object();
```
The first one might be better.
- Two ways to use an element:`myObject["keyName"]` or `myObject.keyName`. Still the first one might be better.

## Exercise - Make a Contact List
- Create a `friends` object and add some friends in it:
```
var friends = {};
friends["bill"] = {};
friends["steve"] = {};
```
- Add properties to your friends:
```
friends["bill"]["firstName"] = "Bill";
friends["bill"]["lastName"] = "KK";
friends["bill"]["number"] = "012345678";
friends["steve"]["firstName"] = "Steve";
friends["steve"]["lastName"] = "BB";
friends["steve"]["number"] = "012345678";
```
- Tosse in an Array: (for adress)
```
friends["bill"]["address"] = ["Bill st", 9];
friends["steve"]["address"] = ["Steve st", 10];
```
- Creating `list` function:
```
var list = function(objectName) {
    for(var keyHolder in objectName){
        console.log(keyHolder);
    }
};
```
- Creating `search` function:
```
var search = function(searchName){
    for(var keyHolder in friends) {
        if( friends[keyHolder]["firstName"] === searchName) {
            console.log(friends[keyHolder]);
            return friends[keyHolder];
        }
    }
};
```

# Objects1
## Reviews and Object
- Lots of reviews: logic, array, for, if ... else(don't do `var = xyz` again), switch(remember to give `(parameters)` after the `switch, remember the `:` for each `case`)......
- We already know numbers, strings, booleans and arrays. Here comes the 5th data type: **object**.
- Creation of an *object*(object literal notation):
```
var myObject = {};
```
- Pass in some value:
```
var myObject = {
    key1: value1,
    key2: value2
};
```
- to access properties: 1.Dot notation: `myObject.key1`, `myObject.key2`...; 2.Bracket notation: `myObject["key1"]`...
- Creation of an *object*(object constructor):
```
var myObject = new Object();
```
- Example to sum it up:  

```
var snoopy ={
    species: "beagle",
    age: 10
}

var buddy = new Object();
buddy.species = "golden retriever";
buddy.age = 5;
```
## Function as Method
- function review:
```
var myFunc = function(param1, param2){
    retern param1 * param2;
};
myFunc(222, 234);
```
- *Properties*: **Variables** associated with an object(Noun, static thing); *Method*: **Functions** associated with an object(Verb, action). Ex:

```
var myFunc = {
    author: "JJJ", // property "author" 
    myAge: 45, // property "myAge"
    multiplier: function(x, y){ // method "multiplier"
        myFunc.myNumber = x * y;
    },
    myBirthYear: function(){
        return (2015 - myFunc.myAge);
    }
}
```
- The **purposes** of using *method* (and not functions):1. Use it to change object property values. 2. Use it  to make calculations based on object properties.(functions can only take *parameters* as input, but method can take object properties directly.) Like the `myBirthYear` method in the above example.(No parameters in that function but we use `myFunc.myAge` directly to do calculation.)
- The `this` key! Use it to make a function reusable in different objects. Ex:

```
var birthYearCalc = function() {
    return (2015 - this.myAge);
};
var jib = {
    myAge: 35,
    myBirthYear: birthYearCalc
};
var kaif = {
    myAge:34,
    myBirthYear: birthYearCalc
};

var jibBirthYear = jib.myBirthYear(); //!!!!!!!!Remember to put () when calling a function/method!!!!!!
alert(jibBirthYear);
var kaifBirthYear = kaif.myBirthYear();
alert(kaifBirthYear);
```
## Object Construction
- JavaScript have it's build-in constructor `Object()` (Use it like `var myNewObj = new Object()`), and we can create our own constructor by creating a constructor function:

```
function Person(name, age) {
    this.name = name;
    this.age = age;
}

var sam = new Person("Sam Perkinson", 45);
```

- Methods can also be pass into a constructor:

```
function Rectangle(height, width) {
    this.height = height;
    this.width = width;
    this.calcArea = function() {
        return this.height * this.width;
    };
    this.calcPerimeter = function() {
        return this.height * 2 +  this.width * 2;
    };
}

var rex = new Rectangle(7,3);
var area = rex.calcArea();
var perimeter = rex.calcPerimeter();
```

## Object with Other Tools
- Arrays of Objects:

```
function Person (name, age) {
    this.name = name;
    this.age = age;
}

var family = new Array();
family[0] = new Person("alice", 40);
family[1] = new Person("bob", 42);
family[2] = new Person("michelle", 8);
family[3] = new Person("timmy", 6);
```
- Loop through the array:(two ways to do this)

```
for(var person in family) {
    console.log(family[person]["name"]);
}

for (var counter = 0; counter < family.length; counter +=1){
    console.log(family[counter].name);
}
```
- Values in an object can be passed into a function.

## Exercise - Building an Address Book
```
function add(firstName, lastName, phoneNumber, email) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.phoneNumber = phoneNumber;
    this.email = email;
}

var bob = new add("Bob", "Jones", "(650) 777-7777","bob.jones@example.com");

var mary = new add("Mary", "Johnson", "(650) 888 - 8888", "mary.johnson@example.com");

var kid = new add("Kid", "Hu", "(33) 9393", "ksd@jig.com");

var contacts = [];
contacts[0] = bob;
contacts[1] = mary;
contacts[2] = kid;

var printPerson = function(person){
    console.log(person.firstName + " " + person.lastName);
};

var list = function(){
    var contactsLength = contacts.length;
    for (var counter = 0; counter < contactsLength; counter += 1){
    printPerson(contacts[counter]);
    };
};

var search = function(lastName) {
    var contactsLength = contacts.length;
    for (var counter = 0; counter < contactsLength; counter += 1) {
        if (lastName === contacts[counter].lastName){
            printPerson(contacts[counter]);
        } else {
        };
    }
};

search("Jones");
list();
```
This is it!!

