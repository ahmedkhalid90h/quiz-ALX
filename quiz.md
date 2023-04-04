# 0x08. C - Recursion
What does this code print?

```
int print(int nb)
{
    if (nb < 0) 
    {
        return (0);
    }
    printf("%d", nb + print(nb - 1));
    nb --;
    return (nb);
}

int main(void)
{
    print(4);
    return (0);
}
```

01234568


> 00246


64200

Question #1
```
What does this code print?

void print(int nb)
{
    if (nb < 0) 
    {
        return;
    }
    printf("%d", nb);
    nb --;
    print(nb);
}

int main(void)
{
    print(4);
    return (0);
}
```

4321


1234


> 43210


01234

Question #2
What does this code print?
```
void print(int nb)
{
    printf("%d", nb);
    nb ++;
    if (nb < 10) 
    {
        print(nb);
    }
}

int main(void)
{
    print(4);
    return (0);
}
```
> 456789


345678910


109876543


987654

Question #3
What does this code print?
```
void print(int nb)
{
    printf("%d", nb);
    -- nb;
    if (nb > 0) 
    {
        print(nb);
    }
}

int main(void)
{
    print(4);
    return (0);
}
```
3210


321


43210


> 4321

Question #4
What does this code print?
```
void print(int nb)
{
    printf("%d", nb);
    nb --;
    if (nb > 0) 
    {
        print(nb);
    }
}

int main(void)
{
    print(2);
    return (0);
}
```
210


> 21


12


012
/////////////////////////////////////////

# 0x09. C - Static libraries


Question #0
What is the format of a static library?


> An archive


A shared ELF file


An executable ELF file


A relocatable ELF file

////////////////////////
Question #1
What command(s) can be used to list the symbols stored in a static library?


ld


> ar


ranlib


> nm

////////////////////////
Question #2
What is the point of using ranlib?


List the content of a library


Create a library from a simple archive


> Indexing an archive


Creating an archive

////////////////////////
Question #3
What command is used to create a static library from object files?


ranlib


gcc


> ar


ld


nm

# 0x0A. C - argc, argv

Question #0
In the following command, what is argv[2]?
```
$ ./argv "My School is fun"
```
is fun


My School


fun


> NULL


is


School


My


My School is fun


./argv

Question #1
In the following command, what is argv[2]?
```
$ ./argv "My School" "is fun"
```
> is fun 


My School


fun


NULL


is


School


My


My School is fun


./argv

///////////////////////

Question #2
In the following command, what is argv[2]?
```
$ ./argv My School is fun
```
is fun


My School


fun


NULL


is


> School


My


My School is fun


./argv

///////////////////////

Question #3
What is argv[argc]?


The first command line argument


> NULL


The program name


It does not always exist


The last command line argument

///////////////////////

Question #4
What is argv[0]


> The program name


The first command line argument


It does not always exist


NULL

///////////////////////

Question #5
What is argv?


> An array of size argc


> An array containing the program command line arguments


An array containing the program compilation flags

///////////////////////
Question #6
What is argc?


The length of the first command line argument


> The size of the argv array


A flag set to 1 when command line arguments are present


> The number of command line arguments

/////////////////////////////////////////////

# 0x0B. C - malloc, free

Question #0
How many bytes will this statement allocate?
```
malloc((sizeof(char) * 10) + 1)
```

21


1


20


10


> 11

////////////////

Question #1
How many bytes will this statement allocate?
```
malloc(10)
```

40


4


> 10


2

////////////

Question #2
How many bytes will this statement allocate?
```
malloc(sizeof(char) * 10)
```

40


20


> 10

/////////////

Question #3
How many bytes will this statement allocate?
```
malloc(sizeof(unsigned int) * 2)
```

> 8


4


2

//////////////////

Question #4
How many bytes will this statement allocate?
```
malloc(sizeof(int) * 10)
```

10


32


> 40

/////////////////

Question #5
How many bytes will this statement allocate?
```
malloc(sizeof(int) * 4)
```

32


> 16


8


4

//////////////

Question #6

What is Valgrind?


It’s a program to test a C program in a specific environment


It’s a new step when I compile with gcc


> It’s a program to validate memory allocation


A container service

/////////////////////////////////////////

# 0x0C. C - More malloc, free

Question #0
You can do this:
```
char str[] = "Best School";

free (str);
```
> No


Yes

/////////////

Question #1
You can do this:
```
free("Best School");
```
> No


Yes

////////////////////

Question #2
What is wrong with this code:


```
int cp(void)
{
    char *s;

    s = malloc(12);
    strcpy(s, "Best School");
    return (0);
}
```
> malloc can fail so we should check its return value all the time before using the pointers returned by the function.


You can’t call strcpy with a string literal


> There is no comment


You don’t have enough space to store the copy of the string “Best School”

//////////////////

Question #3
The memory space reserved when calling malloc is on:


> The heap


The stack

/////////////////////

Question #4
malloc returns an address


False


> True

/////////////////////////

Question #5
malloc returns a pointer


False


> True

//////////////

Question #6
What will you see on the terminal?
```
int main(void)
{
    int *ptr;

    *ptr = 98;
    printf("%d\n", *ptr);
    return (0);
}
```
> Segmentation Fault


It doesn’t compile


98


0

/////////////////////

Question #7
If I want to copy the string “Best School” into a new space in memory, I can use this statement to reserve enough space for it (select all valid answers):


> malloc(sizeof(“Best School”))


> malloc(12)


malloc(11)


> malloc(strlen(“Best School”) + 1)


malloc(strlen(“Best School”))


malloc(sizeof(“Best School”) + 1)

////////////////

Question #8
To allocate enough space for an array of 10 integers (on a 64bit, Linux machine), I can use:


> malloc(10 * sizeof(int))


malloc(10 * int)


malloc(64 * 10)

/////////////////////

Question #9
You can do this:
```
char *s;

s = strdup("Best School");
if (s != NULL)
{
    free(s);
}
```
No


> Yes

# 0x0D. C - Preprocessor

Question #0
What is the gcc option that runs only the preprocessor?


-pedantic


-preprocessor


-a


-p


-cisfun


-P


> -E

////////////////////////

Question #1
What does the macro TABLESIZE expand to?
```
#define BUFSIZE 1020
#define TABLESIZE BUFSIZE
#undef BUFSIZE
#define BUFSIZE 37
```
nothing


> 37


1020

///////////////////

Question #2
The preprocessor removes all comments


False


> True

//////////////

Question #3
This portion of code is actually using the library stdlib.
```
#include <stdlib.h>
```
False


> True

/////////////////////

Question #4
What will be the last 5 lines of the output of the command gcc -E on this code?
```
#include <stdlib.h>

int main(void)
{
    NULL;
    return (EXIT_SUCCESS);
}
```

```
int main(void)
{
 '\0';
 return (0);
}
```

> next right my edit
```
int main(void)
{
 ((void *)0);
 return (0);
}
```
> next right my edit

```
int main()
{
 0;
 return (0);
}
```

```
int main(void)
{
 0;
 return (0);
}
```
///////////////////

Question #5
The preprocessor links our code with libraries.


> False


True

///////////////////

Question #6
The macro __FILE__ expands to the name of the current input file, in the form of a C string constant.


False


> True

///////////////////////

Question #7
The preprocessor generates object code


> False


True

///////////////////

Question #8
This code will try to allocate 1024 bytes in the heap:
```
#define BUFFER_SIZE 1024
malloc(BUFFER_SIZE)
```
False


> True

///////////////////

Question #9
The preprocessor generates assembly code


> False


True

////////////////////////////

Question #10
This is the correct way to define the macro SUB:
```
#define SUB(a, b) a - b
```
> No, it should be written this way:

```
#define SUB(a, b) ((a) - (b))
```
No, it should be written this way:

```
#define SUB(a, b) (a) - (b)
```
No, it should be written this way:


```
#define SUB(a, b) (a - b)
```
Yes

//////////////////

Question #11
What will be the output of this program? (on a standard 64 bits, Linux machine)
```
#include <stdio.h>
#include <stdlib.h>

#define int char

int main(void)
{
    int i;

    i = 5;
    printf ("sizeof(i) = %lu", sizeof(i));
    return (EXIT_SUCCESS);
}
```
Segmentation Fault


sizeof(i) = 5


sizeof(i) = 8


> sizeof(i) = 1


It does not compile


sizeof(i) = 4

////////////////////

Question #12
What are the steps of compilation?


preprocessor 2.compiler 3. linker 4. assembler

> preprocessor 2.compiler 3. assembler 4. linker

compiler 2. preprocessor 3. assembler 4. linker

//////////////////////

Question #13
NULL is a macro


False


> True

///////////////////

Question #14
Why should we use include guards in our header files?


> To avoid the problem of double inclusion when dealing with the include directive.


Because we said so, and we should never ask why.

//////////////////////////////////////////

# 0x0E. C - Structures, typedef

Question #0
Given this code:
```
struct point {
   int x;
   int y;
};
struct point my_point = { 3, 7 };
struct point *p = &my_point;
```
To set the member y of my variable my_point to 98, I can do (select all valid answers):


p.y = 98;


> my_point.y = 98;


> (*p).y = 98;


my_point->y = 98;


> p->y = 98;

//////////////////////

Question #1
Those two codes do the same thing:
```
typedef struct point point;
struct point {
   int    x;
   int    y;
};
point p = {1, 2};
typedef struct point point;
struct point {
   int    x;
   int    y;
};
point p = { .y = 2, .x = 1 };
```
False: the members of the structures will not have the same values


False: the second does not compile


> True

////////////

Question #2
The general syntax for a struct declaration in C is:
```
struct tag_name {
   type member1;
   type member2;
   /* declare as many members as desired, but the entire structure size must be known to the compiler. */
};
```
Maybe


False


> True

/////////////////

Question #3
You should write documentation for all the structures you create


> As soon as I write my structure.


I’ll do it 5 minutes before the deadline when I try Betty on my header file


> True

////////////////////////

# 0x0F. C - Function pointers


Question #0
What does a pointer to a function point to (check all correct answers if there is more than one)?


> The first byte of code of the function


The first character of the name of the function


> code


data

////////////////////

Question #1
This 
```
void (*anjula[])(int, float) 
```
is:


A pointer to a function that takes an int and a float as parameters and returns an empty array


A pointer to a function that takes an int and a float as parameters and returns nothing


> An array of pointers to functions that take an int and a float as parameters and returns nothing


A pointer to a function that takes an array of int and float as a parameter and returns nothing


A pointer to an array of functions that take an int and a float as parameters and returns nothing

///////////////////////

Question #2
If f is a pointer to a function that takes no parameter and returns an int, you can call the function pointed by f this way (check all correct answers if there is more than one):


f;


> (*f)();


> f();

////////////////////////

Question #3
To store the address of this function:
```
void neyo(void);
```
to the variable f of type pointer to a function that does not take any argument and does not return anything, you would do (check all correct answers if there is more than one):


*f = &neyo;


*f = neyo;


> f = &neyo;


> f = neyo;

//////////

Question #4
Which one is a pointer to a function?


(int *)func(int a, float b);


> int (*func)(int a, float b);


int *func(int a, float b);


int func(int a, float b);

//////////////////////////////////////

# 0x12. C - Singly linked lists


Question #0
Arrays Vs Linked Lists: select all true statements


> Memory is aligned for an Array - each elements are back to back in the memory


> We can easily removed an element from a Linked list


> We can add elements indefinitely to a linked list


> Array can contain as value a structure


> Linked list can contain as value a structure


Memory is aligned for a Linked list - each elements are back to back in the memory


We can add elements indefinitely to an array


We can easily remove an element from an Array

/////////////////

Question #1
In a singly linked list, what are possible directions to traverse it? (select all possible answers)


Backward


> Forward

//////////////////////

Question #2
What’s the “tail” of a linked list?


It’s the node with the lowest value


It’s the node with the highest value


It’s the first node


> It’s the node with the pointer to the next equals to NULL

////////////

Question #3
What’s the “head” of a linked list?


> It’s the first node


It’s the last node


It’s the node with the lowest value


It’s the node with the highest value


It’s the node with the pointer to the next equals to NULL

////////////////

Question #4
What’s a node? (select all possible answers)


It’s a cell in an array


It’s a server


It’s an integer


> It’s a structure with a pointer to the next node and value information


> It’s a space allocated in memory