# Style Guide: How To Be Stylish
Much like the clothes you wear, the code you write says a lot about you. If you are dressed like a slob, with shirts that are too big for you and jeans that sag, you will be seen as a slob and generally [treated as such](null "It is a tough life for true slobs."). Much like that, if your code looks like shit, we won't include it in our codebase.

## Readable Code
The goal of all of this is to make code easily readable. We don't want to sift through lines of C in order to figure out what a function you wrote does. This will require two things -- consistency of style and comments. 

## Consistency of Style
There is a lot of contention about what good C code looks like, and there are a ton of different style guides out there. The Linux Kernel, for example, has some weird quirks to it's style --but everyone line of code follows it. Much like the Linux Kernel, our code-base will be unified and from an outsiders point of view will look like [one person wrote all of it](null "That one person will be me. I will get all the credit.").

#### 1. Variables
##### *1.1* Variables will be named with camelCase.
The first letter will be lowercase, and every subword will be capitalized. 

Good: `thisIsAVariableName`
Bad: `This_isA_variable-name`

##### *1.2* Variables will have descriptive names.
Back in the day it was in style to use compact variable names for... well I honestly have no idea why it was in style. Maybe to make the source code a smaller file-size. In any case, we don't do that. Variables should be named such that by looking at it you know exactly what it does.

##### *1.3* All variable definitions will be in the lowest scope possible.
This means if you use a variable only within a `for` loop, define that variable within the `for` loop. The compiler will optimize things for you; you just worry about making things readable.

##### *1.4* Pointers will be named with a lowercase "p" in front, such as pTmp.
No other variable should have a lowercase "p" and then an uppercase letter, which will allow pointers to be easily distinguishable.

##### *1.5* There will be _limited_ global definition of variables.
This means defining variables outside of a function. All global variables will have a lowercase "g" in front of them and then an uppercase letter. Such as `gEverything`.

#### 2. Functions
##### *2.1* Functions will be named with camelCase
Similarly to variables.

##### *2.2* Functions will be defined as either [int or void](null "This is not a hard and fast rule, if there is a VERY good reason to use a different function definition then do so.").

##### *2.3* Functions that can fail will return 0 for success, or -1 for error
If you need to pass a value out, use a pointer in the input arguments. Examples of functions that can fail are functions that make register calls where the ATmega datasheet says there can be a failure. We want to propagate those errors out so we can deal with them.

##### *2.4* Error check all functions
Any time you call a function, ensure that it has not returned an error. If it has, deal with it [appropriately](null "If that means taking off all your clothes and rolling around in mud then do so.")

##### *2.5* Functions will not extend more than 80 lines.
You should be able to see the entire function, with comments, on one screen. If you can't, split it up into multiple functions or make function calls from within it.

##### *2.6* Functions will not have more than 3 levels of indentation.
This is not javascript. I don't want to have to use a super-wide monitor to read your code.

#### 3. Brackets
##### *3.1* Brackets will start on the next line and end on a separate line.
This is possibly the most contested C-style thing in the book. A starting bracket for a function, for loop, if statement, etc. will be on the next line like so:
```
while (1)
{
}
```

It will end on a new line. [There will be no arguing about this](null "There are good arguments to be made, but since I am writing the style guide I get to force it to be in my style.").

#### 4. Spacing
##### *4.1* 4 spaces per every indent.
[Do not use tab characters](null "I will hunt you down and for every tab character you write I will make you write 4 spaces instead."). Every editor will allow you to use your tab-key to insert 4 spaces.

#### 5. Miscellaneous
##### *5.1* No line of code will extend more than 80 characters.
If you really need that monstrous line of code, then split it up with `\`.

BAD:
```
if (thisIsReallyDumb < iCantCode && !(canYouEvenReadThis ? ifYouCanGood : elseYouShouldReadMore))
{
}
```

GOOD:
```
if (thisIsReallyDumb < iCantCode &&\
    !(canYouEvenReadThis ? ifYouCanGood : elseYouShouldReadMore))
{
}
```


##### *5.2* Function calls have the parenthesis directly next to the function name. All other parenthesis will have a space before them.
All user-defined functions will be called with a parenthesis directly after the function name. 

`if`, `for`, `while`, `switch`, and other non-functions will have a space between the function name and the parenthesis. This helps differentiate the fact that they are *not* function calls.

Example:
```
int myFunction(void)
{
    return 0;
}

int main(void)
{
    for (;;)
    {
        myFunction();
    }
}
```

## Commenting: Be Good At It
If you write bad comments, you are [literally the worst person](null "Literally. As in, figuratively literally."). What is a good comment you ask?

#### It is Descriptive

#### It says "why" and not "how"
```
DDRE |= _BV(PE1) // Set pin 10 (PE1) as output
```

The comment above is totally useless. I can look that up in the datasheet. *WHY* is pin 10 being set as an output?

```
// Set pin 10 (PE1) as output
// Using pin 10 to drive an LED to blink
DDRE |= _BV(PE1)
```

Is much more descriptive and is actually useful. 

