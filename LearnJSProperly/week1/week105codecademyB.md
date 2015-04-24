Learn JS Properly
===

# Codecademy.com - JavaScript Track (B)
## 3. LOOP
### 'FOR' Loops
- Doing repetetive jobs. Use loops.
- `for` loop syntax:
```
for(initiation; condition; incrementation){
    DoThis;
}
```
- (Use `i += 1`, to replace `i++`).

### arrays
- to store lists of data, (mix data type is allowed.)
- Position of a data is fixed and ordered.
- Make an array: `var arrayName = [ ];`
- index number starts from "0".
- Use `for` loop for array:
```
var arrayCity = ["a", "b", "4', "c"];
for (i = 0; i < arrayCity;i += 1) {
    console.("I Love you!");
}
```
- The "i" suggested to be used as "iterator".

### Little project "search for your name"
- Variable declaration:
```
var text = "Hey, how are you \
doing? My name is Emily. Emily loves to swim.";
var myName = "Emily";
var hits =[];
```
(the back slash "\\" is to mark a line break.)
- Write the `for` loop to loop through letters in "text":
```
for(i = 0; i < text.length; i += 1) {
}
```
- put the `if` statement inside the `for` loop to search for the first letter of "myName":
```
if (text[i] === myName[0]){
}
```
- Add another `for` loop inside the `if` statement `push` the letters into array "hits":
```
for(j = i; j <= (myName.length + i) ; j += 1) {
    hits.push(text[j]);
}
```
- Log it if no hit:
```
if (hits[0] === ""){
    console.log("Your name wasn't found!");
} else {
    console.log(hits);
}
```
another way for the condition:
```
if(hits.length === 0)
```
And it's done!  
-Think about how to fine-tune it, make sure it only finds the exact matches for you name. How to print out your name in a single string.(search on internet to see if there's already any JS program to do this.)

### 'WHILE' Loops
- `while` loop is used when we don't know in advance how many times we need to loop. Or we want to randomly loop through some code. Ex: coin flips....
- The syntax is:
```
while(condition){
    ACTION;
}
```
- If we use numbers inside ofthe condition. 1 means "true", 0 means "false". Ex: `while(myCondition === 1)` means "while myCondition is true".
- Actually we can just put the variable as condition, and it means that variable is true. Ex: `while(myCondition)` is the same as `while(myCondition === 1)`.
- Pay attention to not creating "infinite loop".
- Set/initiate the condition outside of the loop. Ex:  
```
var myCondition = 0;
while(myCondition < 10){
    ACTION;
}
```
- `for` or `while` is sometimes a matter of preference.

### 'do' / 'while' loop
- To run the code at least ONCE!
- Syntax:
```
do {
    ACTION;
} while (condition);
```
It reads "Do the ACTION once, while the condition is true loop through the ACTION untill the condition becomes false."

### Exercise "Dragon Slayer" game
- ALWAYS start with variables declaration:
1.Checker if we're still slaying. 2.checker if we hit the dragon. 3.damage tracker. 4.total damage tracker.
```
var slaying = true;
var youHit = Math.floor(Math.random() * 2);
// Math.floor(x) function set the number to the largest intenger less than or equal to x.
// Math.random() function randomly pick a floating point number between 0 (include) and 1(exclude).
// So "youHit" will be set to 0 or 1 randomly.
var damageThisRound = Math.floor(Math.random()*5 + 1);
// "damageThisRound" will be a random number between 1 and 5.
var totalDamage = 0;
```
- Add then while loop to start attacking! (Put the action "slaying = false" to make it exit the loop.)
```
while(slaying){
    slaying = false;
}
```
- Inside the `while` loop, `if` you hit the dragon?
```
if(youHit){
    console.log("Hit!!!!!");
} else {
    console.log("RIP.....");
}
```
- `if(youHit)` set "totalDamage" equal to "totalDamage + damageThisRound".
And create another `if` statement, check if totalDamage >= 4, if true, print "You finished it!", else try to get another random "youHit" value, and loop again.
```
totalDamage += damageThisRound;
if(totalDamage >= 4) {
    console.log("You win!");
    slaying = false;
} else {
    youHit = Math.floor(Math.random() * 2);
}
```

- AND IT's DONE!!!
