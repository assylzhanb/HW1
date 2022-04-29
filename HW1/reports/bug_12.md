# BUG-12
## Category
String vulnerability

## Description

`char` arrays are not initialized. And `strcpy` used which can be dangerous. 

## Affected Lines in the original program
In `filter.c:203-206` and `filter.c:228`

## Expected vs Observed
We expect that the char to be assigned ARG_SIZE. However strncpy `strcpy` is too dangerous because it can lead to out-of-bound write.

## Steps to Reproduce
Pass argument with 256 size.
### Command

```
./filter out.png negative (argument that is longer than 255 elements)
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Use `strncpy` instead of `strcpy` and also we should initialize the `char` variables. 