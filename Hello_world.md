# Hello World
### Your first program!

We will now be working on writing your first C program! Although it will be very simple, we will learn a lot about the C language writing it. This program will print out “Hello World” onto the terminal and it will be amazing!

```C
#include <stdio.h>
Int main()
{
    fprintf(stderr, “Hello World!\n”);
    return 0;
}
```
Nice! You just wrote your first C program. You probably don’t know what it does and it most definitely does not work, so let’s break it down.
```C
#include <stdio.h>
```
The first thing we do is the include statement. This line tells the compiler which “libraries” to include when compiling. These libraries are basically additional files that have functions and macros (basically small functions) already written that you can use in your program. We include the `<stdio.h>` library which has super important functionality such as printing to the terminal which we will be doing. Almost every program you have will include `stdio.h` as well as `stdlib.h`, so just get in the habit of including them always. 
```C
Int main() 
{

}
```
Next, we define the main function. [Every](null "well almost…") program has a main function. This is the default function that is called first at runtime and will call all other functions. Think about it as the head of the program and every other part of the program is called from it.
```C
fprintf(stderr, “Hello World!\n”);
```
Here we do the actual work: we print out “Hello World!”. This is where the `#include <stdio.h>` comes in. `fprintf` is a function that, you guessed it, prints out a string of text. Here we are using `fprintf` however there are about half a dozen different `print` functions, but I chose `fprintf` as example to explain output streams. The first argument it takes is `stderr` or “Standard Error”. This is tells the program that whenever it sees a print statement with `stderr` to break the program exactly where it is, print out whatever it needs to, and then continue the program. Other `print` functions wait until the program or section of code has completed before printing out which can get very confusing, especially when debugging. 

But wait Peter, what is that `\n` mean? Well, what a great question young grasshopper! It is an escape sequence that triggers a new line break. There are actually a whole lot of escape sequences:
```
\t  Insert a tab in the text at this point.
\b  Insert a backspace in the text at this point.
\n  Insert a newline in the text at this point.
\r  Insert a carriage return in the text at this point.
\f  Insert a formfeed in the text at this point.
\'  Insert a single quote character in the text at this point.
\"  Insert a double quote character in the text at this point.
\\  Insert a backslash character in the text at this point.
```
Ok now what is that `return 0;` statement mean? It ends the program by telling the program to return 0 to some arbitrary return location. A return statement always indicates the end of a function (or cycle of a recursive function). While this statement isn’t necessary for this example, it’s good practice to return something.


### Let's make it more complex

Now that you understand a bit about the “Hello World!” program, let’s make it a little more complex. We're going to break the printing into a different function and call that in the main in which we’ll learn how to define functions and call functions. 

```C
void print_phrase()
{
    fprintf(stderr, “Hello World!\n”);
    return;
}
int main()
{
    print_phrase();
}
```
In the first part, we define a new function starting by defining its return type. These can be any type, but some common ones are `int`, `boolean`, and `void`. A `void` function returns nothing after executing. Other functions return something of the type defined. 

As you can see, the main function has a return type of `int`. It, however, doesn’t ever display the return `int` it generates. This merely exists as an error check where it will return 0 if successful and another value if it failed. 


