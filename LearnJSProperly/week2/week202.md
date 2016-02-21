Learn JS properly
===

# Beginning JavaScript Chapter 5 - An Object-Based Language

## Native Object Types 2
### Math Object
### Number Objects
### Date Objects
------
Need to come back latter!!!
------

(from page 144)
## Creating Custom Objects
- Constructor: `var jjHuang = new Object();`  
Literal: `var jjHuang = {};` (favor literal then constructor!)  
- Put properties inside:  
```
jjHuang.firstName = "JJ";
jjHuang.lastName = "Huang";
```
- Assign method to the object:
```
jjHuang.greet = function() {
    alert("Hello, my name is " + this.firstName + " " + this.lastName);
}
```
The `function()` has no name: *anonymous function*. 
It can be called using `jjHuang.greet()`.  
The variable `this` is used to refer to the current object (whitch is *jjHuang*.)  
- The whole object with properties and methods can be created at once:  
```
var jjHuang = {
    firstName : "JJ"
    lastName : "Huang",
    greet : function() {
        alert("Hello, my name is " + this.firstName + " " + this.lastName);
    }
};
```
## Create New Types of Objects(Reference Types)
It's an object constructor.  
1. First define a reference type:
```
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}
```
2. Add elements(properties or methods) by using `prototype`:
```
Person.prototype.greet = function() {
    alert("Hello, I'm " + person.firstName + " " + person.lastName);
};
```
3. Create Object using reference types:
```
var jjHuang = new Person("JJ", "Huang");
```
4. Call Object properties by: `jjHuang.firstName`.  
Call Object method by: `jjHuang.greet()`.






