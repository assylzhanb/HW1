# BUG-17
## Category
Arithmetic overflow

## Description

If factor of nmubers is in range `0,1` the image will resize to 0x0.

## Affected Lines in the original program
In `resize.c:22`.

## Expected vs Observed
We expect an image to be resized by factor `0,1` when we use so. but will just resizes to 0.
## Steps to Reproduce
Pass argument factor in the range of `0,1`
### Command

```
./resize input.png output.png 0.002
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Throw error when factor is in range `(0,1)`.