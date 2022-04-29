# BUG-9
## Category
Iteration error

## Description

An index `j` is created outside of the loop.

## Affected Lines in the original program
In `rect.c:64`.

## Expected vs Observed
 We expect that the second `while` loop to work with `j` increment. However `j` is initialized outside of the `while i` loop which causes to not fully iteration of the width (second while loop).
## Steps to Reproduce
Anything
### Command

```
./rect.c poc.png out.png 100 100 77 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Create the `j` index inside of the `while i` loop.