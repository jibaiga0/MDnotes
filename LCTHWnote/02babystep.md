Learn C The Hard Way
===

2. Baby Steps
---

## Formated Printing
The C way of formatting output:
```
#include <stdio.h>

int main()
{
    int age = 10;
    int height = 69;

    printf("I'm %d Y O.\n", age);
    printf("I'm %d inches tall.\n", height);

    return 0;
}
```

Break it down:
- include a "header file" `stdio.h`.
- set variables.
- use `printf` function to print out contents.
- passing in a format string `%d`, and specify the variables to replace it. 

### Extra works
- "ALL" the escape sequences for `printf`:

sequence | char represented
---      | ---
\n       | newline
\t       | horizontal tab
\a       | alarm(beep,bell)
\b       | Backspace
\f       | Formfeed
\r       | Carriage return(CR)
\v       | Vertical Tab
\\       | Backslash
\'       | Single quote
\"       | Couble quote
\?       | Question Mark
\nnn     | octal number of numerical number nnn 
\xhh     | hexa number of numerical number hh

- Conversion Characters/Format specifiers

sequence | print out
---      | ---
%d or %i | decimal integer
%c       | character
%f       | floating point
%s       | string
......

## Valgrind
A debuggin tool for developers.
### Install Valgrind from source.
- unpack valgrind into a folder(`tar -xjvf THE FILE` to unzip tar.bz2 files.)
- cd to that folder and run `./configure`
- run `make` to build it.
- run `make install` to install.

### Useing Valgrind
just run `valgrind THEPROGRAM`
It prints out warnings and errors.



