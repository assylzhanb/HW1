# BUG-6
## Category
Iteration errors

## Description

Iterating over the limit. For loop is iterating till size, not size-1.  

## Affected Lines in the original program
In `filter.c:65` and `filter.c:66`.

## Expected vs Observed
We expect that the for loop we initialized will be iterating till the end of `img->size_y`, but in C it does not work the same as in Python. When we use `<=` it will do more iterations than needed which is not what we expected. 

## Steps to Reproduce
Invoke filter blur or invoke filter negative.
### Command

```
./filter.c poc.png out.png 
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We just need to change the operators `<=` to `<`. This way iteration will not overflow.
