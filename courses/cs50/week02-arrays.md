# Week 02 — Arrays

status: complete

---

## Overview
- storing multiple values of the same type in a fixed, contiguous block of memory.
- this week builds directly on variables and loops from week01, and sets up everything that follows — memory, algorithms, data structures.
- !! STRING LENGTH strlen, i was looking for this during last week's assignment,
but duck50 wouldn't return the reference to me:
manuals.cs50.io/#string.h
- intro #ctype.h
- declare length of array in C, but no need in python
- command line arguments (argc, argv)
- exit status (echo $?)
- cryptography intro


## Key Concepts
- arrays
- indexing (0-based)
- iteration over arrays
- strings as character arrays
- fixed size and its implications


## Mental Models
- arrays = contiguous memory = a row of identically-sized boxes in memory
- index = position, starting at 0
- last valid index is always `size - 1`
- a string is just a char array with a null terminator `\0` at the end
 
---
 
## Code Patterns
 
**Declare:**
```c
int numbers[5];
```
 
**Declare and initialize:**
```c
int numbers[5] = {1, 2, 3, 4, 5};
```
 
**Access element:**
```c
printf("%i\n", numbers[0]);
```
 
**Iterate:**
```c
for (int i = 0; i < 5; i++)
{
    printf("%i\n", numbers[i]);
}
```
 
**String as char array:**
```c
char name[] = {'H', 'I', '\0'};
```
 
**Reusable print function:**
```c
void print_array(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        printf("%i ", arr[i]);
    }
}
```
 
## Common Mistakes
 
- off-by-one: looping with `i <= size` instead of `i < size`
- out-of-bounds access: C won't stop you, but behaviour is undefined
- missing null terminator on manually constructed strings
 
 
## tl;dr
 
- fixed size, set at declaration
- indexed from 0
- elements stored contiguously in memory
- strings are char arrays ending in `\0`
 
---
 
## Exercises
 
### Completed
1. Scrabble - value of each char in string, return winner value
2. Readability - return index (char, word, sentence) within text
 
### Challenges
1. syntax, especially () vs []
2. knowing the breadth of libraries that already exist
 
### Notes on Solutions
- graphical explanation is more helpful, in this instance
- possible my learning style is visual, plus using examples or patterns; 
not simply by verbal explanation
 
---
 
## Questions
 
1. how do i know about different libraries (header files) and therein; 
ie. how would i know which words to learn instead of reading a dictionary
at a certain point, stack overflow, i suppose.
2. at what point is reasonable for one to "give up" and consult other resources?
 
---
 
## Personal Notes
 
multiple engineering friends have pointed out the absurdity of learning C;
whilst trying to remain positive about my learning stage,
i will remain with the belief that this is akin to learning how to be an underwater photographer by starting in the darkroom.
