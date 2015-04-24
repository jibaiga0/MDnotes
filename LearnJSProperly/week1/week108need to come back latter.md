Learn JS Properly
===

# Beginning JavaScript Chapter 18 - Common Mistakes, Debugging, and Error Handling
(was chapter 4 in 4th Edition)

## What we will learn
- Spoting common mistakes!
- Handling runtime errors, or exceptions, with the `try`...`catch` statement.
- Debuging JavaScript with dev tools.
(cope = 對抗、克服)

##  7 Common Mistakes
1. **Undefined Variables.** Always do `var myVari;`.  
2. **Case Sensitivity.** Sometimes it may be difficult to spot it, so always be aware of case.
3. **Braces Paires.** Fomatting your code and make it more readable.
4. **Parentheses Paires.** 
5. **Using `=` Rather than `==`.** It might be legal and not giveing any error. Just the code doesn't work. Check for this problem next time! (And it's even better to use `===`.)
6. **Using a Method as a Property and Vice Versa.** (Actually JavaScript doesn't have methods. What we call *methods* are functions assigned to an object. And we call it *method* to avoid confusion.) Should **not** have `()` after properties, and should have `()` after methods. Ex:  
```
var nowDate = new Date();
alert(nowDate.getMonth());
// getMonth() is a method of Date().
// http://www.w3schools.com/jsref/jsref_obj_date.asp
var myString = "Hello!";
alert(myString.length)
// length is a property of myString.
```
7. **Missing Plus Signs During Concatenation** 

## Error Handling
### Preventing Errors
- Thoroughly check pages in all browsers available. (Or decide which browsers you want to support.)
- Validate your data. Don't make user's input crash your code.
- After all these, code may still go wrong. Ex: Some user firewall issue.... We can use `try`...`catch` to `catch` the bug.
### `try`...`catch` Statements
- `try` and `catch` comes with one another. Can't use them seperatly.
- Use `try` to define a block of code to `try` out, then use `catch` to run codes when an exception occurs. (*Exception* is not an *error*, it means the code didn't ran as expected.)
- If no exception occurs, the `catch` block won't be execute. We can also use this to show exception message to the user.
- Syntax:   
```
try{
    codes to run;
} catch(aVarHere) {
    codes to run if exception catched;
}
```
The `aVarHere` is a variable name by your self to store exception informations.
- The *exception* object contains several properties that provide information about the exception. But *name* and *message* are the most commonly used ones.
- *name* property gives the name of the exception type. And the *message* property gives the exception message.
- But the `try`...`catch` will not work if the code contains already syntax errors.
# NEED TO COME BACK TO THIS CHAPTER LATTER!!!!!!!!
