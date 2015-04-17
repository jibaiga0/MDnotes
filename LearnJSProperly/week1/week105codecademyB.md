# Codecademy.com - JavaScript Track
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
And it's done!!
-Think about how to fine-tune it, make sure it only finds the exact matches for you name. How to print out your name in a single string.(search on internet to see if there's already any JS program to do this.)


