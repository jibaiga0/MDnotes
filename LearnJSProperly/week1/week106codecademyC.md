Learn JS Properly
===

# Codecademy.com - JavaScript Track (C)
## 4. Control Flow
### SWITCH
- We already know `if`, `else` and loops(`for`, `while`).
- If there are multipule/many choices, we can use `switch` statement.
- syntax:
```
var thisVar;
switch(thisVar) {
    case 'OPTION1':
        ACTION1;
        break;

    case 'OPTION2':
        ACTION2;
        break;
    
    default:
        defaultACTION;
}
```

### Logical Operators
- and(`&&`), or(`||`), not(`!`).
- `X && Y` will be true only if `X` and `Y` are both true.
- `X || Y` will be true if one of `X` or `Y` is true, or both true. (Will only be false if `X` and `Y` are both false.)
- `!true` == false, `!false` == true.

### Build "Choose Your Own Adventure"
- Content not really interesting, it doesn't guide you through the thoughts of the programe design...... just note some points:
- use `.toLowerCase()` or `.toUpperCase()` to make the string all lower or upper case, so the comparison will not be case-sensitive.
- The game structure: 1. A `prompt` for 3 choices. 2. A `switch` statement to determin what to do in all cases. 3. Each choice have an `if`...`else` statement to let user choose from.
