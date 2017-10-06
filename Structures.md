# Structures
While C is not at all an object oriented language, there are some tricks that you can use to get around this. One of those tricks is structures. While structures are actually just a collection of different types under a single name, it can help to think about them as pseudo-objects. To create a structure, you define it using the `struct` keyword:
```C
struct structure_name 
{
    data_type member1;
    data_type member2;
    .
    .
    data_type memeber;
};
```
So what data types can you use? Well, you can use any! Even structures can be data types defined within a structure definition! Usually, and to keep it simple, structures are defined with `int`, `char`, `float`, etc. Here’s an example of a person being defined as a structure with a name, citNo, and a salary:
```C
typedef struct person
{
    char name[50];
    int citNo;
    float salary;
} person;
```
To access the data inside a structure, you use the `.`. So to access the salary of say `person1` you would do `person1.salary`. As simple as that.

Structures are pretty cool and very powerful! But, they can be made even more powerful by using pointers. By using pointers, instead of moving around a whole structure (which can get very large), your program will be more lightweight, run faster, and just better in general. So here’s how you do it:
```C
typedef struct person_ptr *person;

typedef struct person
{
    char name[50];
    int citNo;
    float salary;
} person;
```
Just like before, we define the person structure with all the data that will go in it. We also define another structure type that is the `person_ptr` which is merely a variable. The `*` however, as you know, will create a pointer of the person object. Now when create a person structure, and want to use a pointer instead of the full structure you do this:
```C
Person_ptr person1;
person1->name = …
person1->citNo = …
person1->salary = ...
```
Notice here how we use the `->` instead of the `.` to access and modify the information stored within the structure pointer. 

