# BUG-15
## Category
Unchecked system call returning code

## Description

`malloc()` function is never checked if it was successfull. Which can lead to segmentation fault.

## Affected Lines in the original program
In `solid.c:12`.

## Expected vs Observed
We expect that the `malloc()` will allocate a memory. However, we never check if it was successful.

## Steps to Reproduce
Anything.
### Command

```
Any
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
Check if the `malloc()` was successful. call an error or return `NULL`. 