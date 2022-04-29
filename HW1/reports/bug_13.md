# BUG-13
## Category
Command injection

## Description

System call are used in the code. 

## Affected Lines in the original program
In `solid.c:125`.

## Expected vs Observed
We expect that the system command functions will give us information about the file. However, it can be easily intervened by putting other flags in `stdin`. This will result in unwanted results. 


## Steps to Reproduce
Pass --help or other commands in `stdin`.
### Command

```
./solid --version 50 50 70 000000
```
### Proof-of-Concept Input (if needed)
Any file.

## Suggested Fix Description
We should remove system calls and use alternative information source functions such as `stat`.