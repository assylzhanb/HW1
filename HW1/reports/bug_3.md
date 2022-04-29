# BUG-3
## Category
Wrong operators

## Description

Wrong choice of operators in the line 49 in the file `resize.c` which leads to incorrect calculation of pixels. 

## Affected Lines in the original program
In `resize.c:49`

## Expected vs Observed
We expect that the malloc will provide enough space for `n_pixels` amount by multipliying the count of pixels to the size of one `pixel`. However, the original code uses `addition` instead of `multipliying` which will probably end up with not enough space for the number of pixels. 

## Steps to Reproduce
Anything.
### Command

```
./resize poc.png out.png 15
```
### Proof-of-Concept Input (if needed)
(attached: poc.png)

## Suggested Fix Description
We just need to change `malloc(n_pixels + sizeof(struct pixel))` to `malloc(n_pixels * sizeof(struct pixel))`. This will allow to create right amount of space for `px`. 
