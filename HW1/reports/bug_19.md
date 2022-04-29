# BUG-19
## Category
Arithmetic overflow

## Description

If width is 0 then the image will be 0x0

## Affected Lines in the original program
In `solid.c:49`.

## Expected vs Observed
We expet the program to error if 0. But works and makes an image 0x0. Which is incorrect behavior.


## Steps to Reproduce
Pass argument 1 `width` with the value 0
### Command

```
./solid out.png 20 0 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We should check if the width is equal to 0.