# File Structure
In C, it is often very beneficial to split your code into different documents so you can keep your main file clean. For this, we will be creating `.h` files. These are basically extended C files that you might store all your helping functions, data structure definitions, and macros. The file acts the exact same as a regular C file, and is important into a file. Let’s generate an example where we have a `main.c` file and a `helper.h` file. 

Here’s the `main.c` file:
```C
#include <stdio.h>
#include “helper.h”

int main()
{
    print_name(“Peter”);
    return 0;
}
```
And here is the `helper.h` file:
```
void print_name(name)
{
    fprintf(stderr, “%s\n”, name);  // prints name
}
```
As you can hopefully see, the main function (the first one the computer runs) calls a function, `print_name`, which is located in the other file. Note the `#include “helper.h”` line near the top. This tells the compiler to include the `helper.h` file and all the functions within it.

What’s cool about this file structure is that you can include advanced libraries that other people have made and use all the functions that they wrote in your code. That’s exactly what we do at OEM like, for example, we include our CAN library, AVR libraries, and other libraries so that we have access to advanced functions that saves us a whole load of time and simplifies our code.

