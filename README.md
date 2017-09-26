# C Tutorials
Come here to learn more about the C language!

## Setting up your environment
The beautiful thing about C is that you don't really need that much to get started! Since C is at the core of most common languages (Java, Python, C++, etc.) in some form, it is already installed on your computer!

The biggest requirement to writing C on OEM is to be writing it in either OSX or a Linux based OS. We require this mostly so that we can accurately troubleshoot you when it comes to that. 

The only thing that you do need to install is a compiler which turns your code into something that is readable by the computer. For this, we'll install the GNU GCC compiler, which is by far the most popular and easy to use compiler.

```
$ sudo apt-get update
$ sudo apt-get install build-essential manpages-dev
```
*note that the `$` specifies a command that is being run on the terminal comand line.*

To verify that you correctly installed the gcc compiler, run

```
$ gcc --version
```

The only thing you need then to write C code before compiling is a text editor. You can use whatever text editor you would like. Some common ones are Atom, Sublime, or VIM. The only thing we ask is that you write good code that follows the OEM [C Style Guide](Style_guide.md).

## Lessons
- [Lesson 1 - Intro](Intro.md)
- [Lesson 2 - Hello World](Hello_world.md) 
- [Lesson 3 - Compiling](Compiling.md) 
- [Lesson 4 - Logic](Logic.md)
- [Lesson 5 - File Structure](File_structure.md)
- [Lesson 6 - Data Types (Or there lack of...)](Data_types.md)
- [Lesson 7 - Stack, Que, and Arrays](Stacks_etc.md)
- [Lesson 8 - Pointers](Pointers.md (coming soon))
- [Lesson 8 - Structures](Structures.md (coming soon))
