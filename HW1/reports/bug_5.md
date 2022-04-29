# BUG-5
## Category
Type errors

## Description

Passing `char*` argument to parameter of type `char**`. This will confuse the `strtol` function.

## Affected Lines in the original program
In `rect.c:35`.

## Expected vs Observed
We expect to create a `hex_color` variable that will continue till the last element. To achieve this we use `strtol()` function that takes three arguments one of which is `char**` but end_ptr that we pass is `char*`. Initial code's behavior is unknown because the `strtol()` that receives a simple pointer would be a complete mess. 

## Steps to Reproduce
Anything
### Command

```
./rect.c poc.png out.png 70 80 90 20 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We just have to change `strtol(argv[7], end_ptr, 16)` to `strtol(argv[7], &end_ptr, 16)`. This way our expectations will come true because now strtol receives the address of the pointer. 
