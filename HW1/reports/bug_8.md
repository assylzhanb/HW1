# BUG-8
## Category
Iteration error

## Description

`i` index is incrementing outside of the scope it should be within. 

## Affected Lines in the original program
In `rect.c:80`.

## Expected vs Observed
We expect to iterate over the height of the rectangle using `i`. However, `i++` is located out of the `for loop` scope. 
## Steps to Reproduce
Anything
### Command

```
./rect.c poc.png out.png 100 100 77 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Change `i++` incrementing outside of the `j` loop. 
