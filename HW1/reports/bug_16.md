# BUG-16
## Category
Arithmetic overflow

## Description

`unsigned short` cannot be assigned to numbers more than `USHRT_MAX`. 

## Affected Lines in the original program
In `resize.c:34` and `resize.c:35`.

## Expected vs Observed
We expect to make a variable to be assigned to the dimensions of resized image. If put too much it will overflow. 

## Steps to Reproduce
Resize an image with very large factor. 
### Command

```
./resize input.png out.png 1000
```
### Proof-of-Concept Input (if needed)
png with 200x1000

## Suggested Fix Description
We should check for the result of multiplication. 