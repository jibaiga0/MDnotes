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
