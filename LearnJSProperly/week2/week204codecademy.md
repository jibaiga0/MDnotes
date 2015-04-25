Learn JS properly
===

# Codecademy JavaScript track
# Object 2 
## Object review
- Create object with *Literal notation* or *Constructor notation*
- Add method into an object. Also have *Literal notation* and *Constructor notation*.
- the use of `this`.
- *dot* notation and *bracket* notation.

## Some more about Object
- Use `typeof` to check the type of something. Ex:
```
var aNumb = 33;
var anObj = {};
console.log(typeof anObj + " " + typeof aNumb);
```
- The `hasOwnProperty()` method:
```
var anObj = { name:"jj" };
console.log(anObj.hasOwnProperty('name')); //will print out true.
console.log(anObj.hasOwnProperty('nickname')); //will print out false.
```
- Some more review of `for`...`in` loop:
```
for(var myPlaceHolder in myObject){
    console.log(myPlaceHolder);
}
```
and use the `for`...`in` loop to get the values:
```
for(var myPlaceHolder in myObject){
    console.log(myObject[myPlaceHolder]);
}
```

## Time for OOP
### Class and Prototype
- **Class** = *type*, or a *category of objects*.
- Making an object constructor is to create a *class*.(the `Circle()` constructor can also be think of as a `Circle` class.)
```
function Circle(radius){
    this.radius = radius;
}
```
- The *class* (as in a constructor) helps us to know what can we do and what we have in the objects from this particular *class*.
- **Prototype** keeps track of what a given class can or can't do, and what a class has or doesn't have.(JavaScript automatically defines the prototype for class with a constructor.)
```
function Dog(breed){
    this.breed = breed;
}
var buddy = new Dog("Golden Retriever");
buddy.bark = function() {
    console.log("Woof");
};
buddy.bark();
var snoopy = new Dog("Beagle");
snoopy.bark();
```
The above code set a `Dog()` constructor/class. Create a dog called buddy, and teach it to bark. But since we didn't teach snoopy to bark, the `snoopy.bark()` method will not work!
To make all dogs bark after the creation of the constructor, we can use `prototype`: (`OBJECT.prototype.METHODNAME`)
```
function Dog(breed){
    this.breed = breed;
}
Dog.prototype.bark = function(){
    console.log("Woof");
};
var buddy = new Dog("Golden Retriever");
var snoopy = new Dog("Beagle");
```
Now we use `prototype` to add a method into the constructor, so that both dogs can bark!

### Inheritance
- **Inheritance** allows one class o see and use he methods and properies of another class.

