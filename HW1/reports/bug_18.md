# BUG-18
## Category
Arithmetic overflow

## Description

If height is 0 then the image will be 0x0

## Affected Lines in the original program
In `solid.c:49`.

## Expected vs Observed
We expec thte program to error if 0. But works and makes an image 0x0. Which is incorrect behavior.


## Steps to Reproduce
Pass argument 1 `height` with the value 0
### Command

```
./solid out.png 0 20 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We should check if the height is equal to 0.