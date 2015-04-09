Learn C The Hard Way
===

3.Set Up The Foundation
---

## C Program Structure
```
#include <stdio.h>
/* A comment. */
int main(int argc, char *argv[])
{
    int distance = 1000;
    printf("U R %d miles away.\n", distance);

    return 0;
}
// another comment
```

Break It Down:
- import another file/function into this file.(`.h` for "header" files.)
- `/* XYZ */` is a multi-line comment.
- more "complex" version of `main` function, specifing the "ARGUMENTS". (What do they mean?)
- between `{` and `}` is the function's body.
- Variable declaration. Syntax : `type name = value;`. Statements end with a `;`.
- `printf`, like always. Function call syntax: `name(arg1, arg2);`
- `return`
- `//` single line comment.

### Something I don't know about the code
`(int argc, char *argv[])`

int argc = ARGument Count as INT?  
char \*argv[] = ARGument V??? as CHAR in Array.  
(according to the error message printed out by make, `char *` seems to represent "string".)

## Variable Types

Type   | Value example | how to print
---    | ---           | ---
int    | 999           | %d or %i
float  | 2.3458        | %f
double | 44322.43      | %f
char   | 'H'           | %c
char   | "Jass"        | %s

**The "string" is declare with `char name[]`**

example code:
```
#include <stdio.h>

int main(int argc, char *argv[])
{
    int distance = 100;
    float power = 2.345f;
    double super_power = 56789.4532;
    char initial = 'A';
    char first_name[] = "Zed";
    char last_name[] = "Shaw";

    printf("You are %d miles away.\n", distance);
    printf("You have %f levels of power.\n", power);
    printf("You have %f awesome super powers.\n", super_power);
    printf("I have an initial %c.\n", initial);
    printf("I have a first name %s.\n", first_name);
    printf("I have a last name %s.\n", last_name);
    printf("My whole name is %s %c. %s.\n",
    first_name, initial, last_name);

    return 0;
}
```

