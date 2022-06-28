# BUG-7
## Category
Local persisting pointers

## Description

A function that returns the address of a local variable which is not correct. 

## Affected Lines in the original program
In `filter.c:112`.

## Expected vs Observed
We expect that the function `get_pixel` will return a pointer for a new allocated pixel. But, the function does not use `malloc` but just declares a variable. 
## Steps to Reproduce
Run negative
### Command

```
./filter.c poc.png out.png negative 20
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Use `malloc` to allocate new memory.
