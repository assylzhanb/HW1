# BUG-2
## Category
Heap overflow/underflow

## Description

Accessing `argv[7]` is out of bounds and causes heap overflow.

## Affected Lines in the original program
In `circle.c:30`

## Expected vs Observed
We expect that the loops process over all the pixels in the image by iterating
over every row, and every pixel in that row, starting from index 0. The loop
counters are not initialized and are thus not guaranteed to start at 0. This
makes the behavior of the grayscale filter undefined.

## Steps to Reproduce
Anything
### Command

```
./circle input.png out.png 100 100 77 000000
```
### Proof-of-Concept Input (if needed)
Any file 

## Suggested Fix Description
Change `strtol(argv[7],&end_ptr, 16)` to `strtol(argv[6], &end_ptr, 16)`. This will prevent the code from going beyond the end of the input. i.e. we should provide a correct index for hex_color.