# BUG-14
## Category
Stack overflow

## Description

`out_name` has fixed size. putting more than that will lead to stack overflow. 

## Affected Lines in the original program
In `checkerboard.c:34`.

## Expected vs Observed

We expect that the size of output file is 500. However if we pass 500+ characters it will lead to stack overflow.


## Steps to Reproduce
Pass an output name with 500+ length.
### Command

```
./solid iiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiii 20 20 0000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Don't set a limit or use `strncpy` instead of `strcpy`.