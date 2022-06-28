# BUG-10
## Category
Heap overflow

## Description

Trying to write out of bound

## Affected Lines in the original program
In `checkerboard.c:68`.

## Expected vs Observed
We expect to build a checkerboard, but the `square_width` is larger than `width and height`.
## Steps to Reproduce
Pass argument with `square_width` larger than both `width` and `height`.
### Command

```
./checkerboard out.png 50 50 70 000000 FFFFFF
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We should add an instruction that checks if `square_width` is bigger than `width and height`.