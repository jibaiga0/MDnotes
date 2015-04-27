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
- **Inheritance** allows one class to see and use the methods and properies of another class.
- Take *ANIMAL* and *DOG* for example. Normaly if we want to add a method called *sayName* to *ANIMAL* and *DOG*, we do it as follow:
```
// Create an Animal() object.
function Animal(name, numLegs) {
    this.name = name;
    this.numLegs = numLegs;
};
Animal.prototype.sayName = function() {
    console.log("Hi my name is " + this.name);
};
// Crete a Dog() object.
function Dog(name, numLegs){
    this.name = name;
    this.numLegs = numLegs;
};
Dog.prototype.sayName = function() {
    console.log("Hi my name is " + this.name);
};
```
Seems like we are doing many retyping...
- Here comes the *prototype* again:
```
function Animal(name, numLegs) {
    this.name = name;
    this.numLegs = numLegs;
};
Animal.prototype.sayName = function() {
    console.log("Hi my name is " + this.name);
};

function Dog(name){
    this.name = name;
    this.numLegs  = 4;
};
Dog.prototype = new Animal();
```
And now we can use `sayName()` function in the `Dog` object.
- The **Prototype Chain** dogs are animals, and racing dogs are dogs, so racing dogs are also animals!
So we can make `racingDog` inherent from `Dog`, and `Dog` inherent from `Animal`. So that `racingDog` can also use the properties or methods from `Animal`.
```
function Animal(name, numLegs) {
    this.name = name;
    this.numLegs = numLegs;
    this.isAlive = true;
};
function Dog(name){
    this.name = name;
    this.numLegs  = 4;
};
function racingDog(name){
    this.name = name;
    this.saying= "WOOOOOF!";
}
Dog.prototype = new Animal();
racingDog.prototype = new Dog();

var thunder = new racingDog("Thunder");

console.log(thunder.saying);
console.log(thunder.numLegs);
console.log(thunder.isAlive);
```

### Public or Private
- Object properties are **Automatically Public**, it can be accessed everywhere in the code.
- How ever, we can create **Private** variables whitch can only be accessed from within the object.
```
function Person(first, last, age){
    this.firstname = first;
    this.lastname = last;
    this.age = age;
    var bankBalance = 7500;
    // this makes bankBalance a Private variable.
}
var john = new Person("J", "H", 77);

console.log(john.age);
console.log(john.bankBalance);
```
The property "bankBalance" is not accessable outside of the object, so the code `console.log(john.bankBalance);` will print out "undefined".
- If we want to access private properties, we can do it by creating a public method:
```

