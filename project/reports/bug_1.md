# BUG-1
## Category
Temporal memory safety violation

## Description

`free()` called two times.

## Affected Lines in the original program
In `checkerboard.c:147`

## Expected vs Observed
We call a function `free()` to free the allocated space after using `malloc()`. However, after we call `free(img)`, we invoke an error, then the `free()` is duplicated which causes error.
## Steps to Reproduce

We should create a large enough input to invoke allocation error `error_img`. this will allow to the program to read through double `free()` function.

### Command

```
./checkerboard 40000 50000 1000 000000 FFFFFF
```
### Proof-of-Concept Input (if needed)


## Suggested Fix Description
Remove the second `free()` function. 
