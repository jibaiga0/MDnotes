Learn C The Hard Way
===
1. First Step
---

## Set Things Up
On linux machine:

```
sudo apt-get install build-essential
```

### Don't Use IDE
like "staff notation" vs "guitar tabs" in music.(not really a good example...)

## Learn to use compiler
Write a "Hello World." programe as learning all other languages:
```
int main(int argc, char *argv[])
{
    puts("Hello world.");
    return 0;
}
```

save it as `hello.c` and then MAKE it!
```
make hello
```

then run it by typeing:
```
./hello
```

###  _The "HOW TO BREAK IT" section_

remove the `hello` file
then type:
```
CFLAGS-"Wall" make hello
```
for the "implicit declaration" warning, add `#include<stdio.h>` at the begning of the file.

## Make basics
use the command
```
CFLAGS="-Wall" make hello
```

The part `CFLAGS="-Wall"` is to pass a **modifier** as **environment variables**. 
This adds the option `-Wall` to the `cc` command that `make` runs. and it tells the compiler to report all warnnings!

### Makeing a Makefile
create a document called `Makefile`.
enter:
```
CFLAGS=-Wall -g

clean:
    rm -f hello
```

What's inside:
- setting the `CFLAGS`.
- add a `-g` flag to get debugging.
- add a `clean` section(can name it whatever you want, but it seems like a good practice to name it "clean").

**Warning : in tht makefile, Make sure you are only entering TAB characters, neither spaces nor mixtures of TAB and spaces. And ALWAYS INDENT!**
