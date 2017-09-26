# Stack, Que, and Arrays
All these items are very important when it comes to fundamental C and embedded firmware. What’s cool about these coming data types is that they can take any data type into them. So an array, could be an array of ints, floats, or some random data type you make up yourself. 

### Stack
A stack is a data type in which you add elements to it, and read them from the reverse order as adding them. It’s what’s called a “last in, first off” data type. Image a tube that can hold ping pong balls that is mounted to a table. You begin adding balls to the tube and eventually you want to remove some. You obviously cannot remove the bottom ball because you can’t reach it, so you have to remove all the balls on top of it. 
![Stack](stack_representation.jpg)

There are only two basic operations that you can perform on a stack: `push()` and `pop()`. `push()` adds a new element to the stack and `pop()` removes the top element. In addition you can perform these three operations:
```C
peak()      # gets the top data element without removing it
isFull()        # checks if the stack is full
isEmpty()   # checks if the stack is empty
```

### Que
A que, unlike a stack, is open on both ends. This means that whatever data you added first, is the first data to be removed. This is also known as “first in, first out” or “last in, last out”. 

![Queue](queue_diagram.jpg)

Imagine a line of cars going into a tunnel: the first car into the tunnel is also the first car out of the tunnel and the order of the cars cannot change in the tunnel. The basic functions are:
```C
enqueue()   # adds an item to the que
dequeue()   # removes an item from the que
```
There are a few other functions that add a lot of functionality to ques:
```C
peek()      # gets the element at the front of the queue without removing it
isFull()        # checks if the queue is full
isEmpty()   # checks if the queue is empty
```

### Arrays
An array is a data structure which is more advanced than the previous ones because it allows you to access data in any location in array. While arrays are significantly more advanced (and most of the time also more useful), they are also larger and take up more space.
![Array](array_representation.jpg)
As you can see, arrays start their lives when you define them. Arrays can be filled with any data type which unlocks a whole bunch of functionality. In this case, the type of data in the array is of type `int`. The next thing you define is the size of the array you want. Unlike other languages like python where it is able to dynamically allocate memory for you array, C forces you to allocate space even before you begin filling it. In this case, we’re going to define `[10]` bits for this array.
Lastly, you can begin filling your array with data of any type.

What makes arrays so powerful is the functionality that they provide once your data is in there.
Here are the basic operations you can write to perform on an array:
>Traverse - prints all the array elements one by one

> Insertion - adds an element at a given index

> Deletion - deletes an element at the given index

> Search - searches an element using the given index or by the value

> Update - updates an element at the given index

