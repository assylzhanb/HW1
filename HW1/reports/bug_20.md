# BUG-11
## Category
Arithmetic overflow

## Description

`long` type overflows when putting very large numbers in `square_top_left_y` and `square_top_left_x`. 

## Affected Lines in the original program
In `checkerboard.c:109`.

## Expected vs Observed
We expected that the function will color the squares. However, it overflows when the `int` capacity is overflowed. 
## Steps to Reproduce
Run a code with `square_width` larger than `INT_MAX`

### Command

```
./checkerboard out.png 200 200 400000000 000000 FFFFFF
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Change `i++` incrementing outside of the `j` loop. 
