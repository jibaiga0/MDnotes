Learn JS properly
===

# JavaScript is Sexy - JavaScript Objects in Detail  
## What is **Object**
- The *core* data type in JavaScript
- **complex** data type: object.  
**pirmitive** data type: Number, String, Boolean, Undefined, Null ...(only 4 or more?)
- **Object** is: an unordered list of primitive datas, stored as *name-value* pairs. The items are called *properties*( functions are called *methods*.)  
(Numbers can be used as item's name, but can only be called with bracket notation, but not dot notation.)

## Reference Data Type vs Primitive Data Types
The value of *Reference data type* is stored as a reference, but not directly assign to the variable. Ex:
```
var iAm = "JJ";
var youAre = iAm;
iAm = "BB";
alert(iAm); // will give "BB"
alert(youAre); // will give "JJ"
```
The value of "iAm" is copied to "youAre", so the changes to "iAm" doesn't chage the value of "youAre".
```
var iAm = {name:"JJ"};
var youAre = iAm;
iAm.name = "BB";
alert(iAm.name); // will give "BB"
alert(youAre.name); // will also give "BB"
```
The object "youAre" is just pointing(refencing) to the object "iAm". So when the property of "iAm" changes, the property of "youAre" also changed.  
Also, if we cahnge the properties inside the object "youAre", the same properties inside the object "iAm" will also be changed!
```
youAre.name = "CC";
alert(youAre.name); // will give "CC"
alert(iAm.name); // will also give "CC"
```

## Object Data's Properties Have **Attributes**
1. Configurable: if it's changable or deletable.
2. Enumerable: if it's possiable to be reurned in a `for`...`in` loop.
3. Writable: if it's changable.
(They are set to TRUE by default.)

## Creating Objects
1. Object Literals
2. Object Constructor
(SEE OTHER NOTES!!)

## Practical Patterns for Creating Objects
It's used to make repetitive work easier.(So we don't need to create 10 object of the same kind manualy.)
1. Constructor Pattern:
```
function Fruit (color, name) {
    this.color = color;
    this.name = name;
    this.showName = function(){
        alert("This is a " + this.name);
    }
}
```
And we just creat new fruit by doing:
```
var mango = new Fruit("Yellow", "Mango");
```
2. Prototype Pattern:
```
function Fruit(){}
Fruit.prototype.color = "non";
Fruit.prototype.name = "not a fruit";
Fruit.prototype.showName = function(){
    alert("This is a " + "this.name);
}
```
(doesn't looks like a very good example...)
---
FURTHER READING:
### Chapter 6 of *Professional JavaScript for Web Developers*

