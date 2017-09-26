# Compiling
Unlike other, more modern, languages, C relies on a compiler to turn your raw code into commands that can be executed by a computer. This is called compiling. The most common compiler for C is the GNU GCC compiler. Here is how you install it:
```
$ sudo apt-get install build-essential manpages-dev
```
Then make sure you installed it correctly by running
```
$ gcc --version
```
Now that you have the compiler installed, let’s learn how to use it! Going back quickly to your `hello world!` example, let’s save that code as `hello.c`. Congratulations, you just saved your first C file! Now let’s compile it:
```
$ gcc hello.c -o name-of-your-choice
```
The first part of this command is `gcc` which tells the computer that you are going to be compiling with the gcc compiler. Next you specify what you are going to be compiling. We are going to be compiling our new `hello.c` file that we just saved. Next we’re going to specify what kind of output we want gcc to create. In this case we are creating an output file that can be executed like a normal program. Lastly, we specify what we want the output file to be called; you can specify any name you want, but make sure it’s something that makes sense or tells you what the program will do. Now let’s run it.
```
$ ./name-of-your-choice
```
That should run your program and you should see `hello world!` printed in the terminal!


