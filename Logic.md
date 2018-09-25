# Logic
### If statement
One of the most important things to learn about programming in general is logic or logic flow. These chunks of code “point” your program along its path of computation. Logic tests “cases” or certain events that the programmer defines and wants the program to catch, do something, and then continue. 
```C
if  (testExpression)
{
    // do something;
}
```
The first logical is the `if` statement. This statement works exactly as you might expect. If the case returns true, it executes whatever is between the curly braces, and if it’s false, it will skip over the curly braces onto the next statement. 
### Else statement
```C
if (testExpression)
{
    // do something
} else {
    // do something else;
}
```
The next logical to learn is the `else` statement. Note that the `else` statement cannot stand on its own and must be preceded by an `if` statement. Just like the `if` statement the `else` statement does exactly as it sounds. If the `if` statement’s `testExpression` evaluates to false, the `else` statement will be run. The `if` and `else` statements often come in pairs, although good programmers can structure their code to only use `if` statements to eliminate all cases to one and evaluate that. 

Both the `if` and `else` statements can be nested within each other allowing complex logic flow to deal with cases. 

### While loops
```C
while (testExpression)
{
    // do something;
}
```
The `while` loop is also one of the most important flow controllers that exist in C. What’s nice, however, is that, like the other two logicals discussed, it works exactly as you might guess. While the `testExpression` evaluates to true, the code within the curly braces is evaluated. What complicates things with the `while` loop is that they are continually looped back until the `testExpression` evaluates to false. Here is where “infinite while loops” are created. Basically, when the developer doesn’t realize that the `testExpression` will never evaluate to false, the loop will go on forever or until the runtime “core dumps”. 
### For loops
```C
for (initializationStatement; testExpression; updateStatement)
{
    // do something;
}
```
The `for` loop is one of the most complex, but also powerful flow controllers because it combines the power of the `while` loop with `if` statements. The `for` loop starts by creating an `initializationStatement` which often is a temp variable that you will loop through. The `testExpression` is the `if` statement where you evaluate a logical expression each time. The `updateStatement` is what you want to change each time you loop through it. Most frequently this increments a variable by a certain count amount. To demonstrate how the `for` loop works, here’s a demo that prints the numbers 1-10.
```C
for (int i = 1; i <= 10; i++)
{
    fprintf(stderr, "%d",i);
}
```

