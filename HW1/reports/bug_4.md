# BUG-4
## Category
Wrong operators

## Description

Wrong choice of operators in the `circle.c` file in the lines 87 and 63. The variables are not assigned but compared to the values. 

## Affected Lines in the original program
In `circle.c:63` and `circle.c:87`.

## Expected vs Observed
We expect that the variables y is assigned to round`(center_y - sqrt(radius * radius - (x - center_x) * (x - center_x)))` and x is assigned to `sqrt(radius * radius - (y - center_y) * (y - center_y)))` But instead of this the original code just checked if they are these values with `==` operator. 

## Steps to Reproduce
Anything
### Command

```
./circle poc.png out.png 100 100 70 000000
```
### Proof-of-Concept Input (if needed)
Anything

## Suggested Fix Description
We need to change `==` operators to `=` operator. This will allow x and y to be assigned properly. 
