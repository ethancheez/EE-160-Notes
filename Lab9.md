# Lab 9
Lab 9 will be due 10/27

## switch case
- This is essentially a different method of writing if statements
- MUST HAVE `break;` after every case.

Example:
```c
int var;

switch(var) {
  case 1:
    break;
  case 2:
    break;
  case 3:
    break;
  case 4:
    break;
  case 5:
  case 6:
    break;
    
  default:
    break; //optional
}
```
This is equivalent to:
```c
int var;

if(var == 1) {
  //case 1
} else if(var == 2) {
  //case 2
} else if(var == 3) {
  //case 3
} else if(var == 4) {
  //case 4
} else if(var == 5 || var == 6) {
  //case 5 OR 6
} else {
  //default
}
```
- a switch case is used for one variable so you can't really do an "&&" (AND) operator because the same variable cannot equal two different things.
  - If you want to have a "&&" with two variables, you can just put an if statement inside the case.
Example:
```c
int a = 1;
int b = 2;

switch(a) {
  case 1:
    if(b == 2)
      //some code
    break;
  case 2:
    break;
}
```

## driver1
- Files Included:
  - driver1.c
  - mygrader.c
  - mygrader.h

Compile with makefile:
```bash
make driver1
```
Run Program:
```bash
./driver1 < mygrader.dat
```
Example Output:
```
95: A
85: B
80: B
75: C
70: C
68: D
50: F
104: illegal score
-10: illegal score
```

## driver2
- Files Included:
  - driver2.c
  - mygrader2.c
  - mygrader2.h
  
Compile with makefile:
```bash
make driver2
```
Run Program:
```bash
./driver2 < mygrader2.dat
```
Example Output:
```
95: A
85: B
80: B
75: C
70: C
68: D
50: F
104: illegal score
-10: illegal score
Passing Scores: 5
Failing Scores: 2
Illegal Scores: 2
```

## countgrades
- Files Included:
  - countgrades.c
- After entering all the inputs, press [CTRL+D]

Example Output:
```
abcDFEGH
DdFFEEaA
[CTRL+D]
Grade counts:
  A's: 3
  B's: 1
  C's: 1
  D's: 3
  F's: 3
  Other grades: 5
```

## Files to Submit
| .c Files | .h Files |
| :---: | :---: |
| mygrader.c | mygrader.h |
| mygrader2.c | mygrader2.h |
| driver1.c | |
| driver2.c | |
| countgrades.c | |

and your makefile...

# Submission
```bash
grade -lab9s1,ee160  *.c *.h makefile
```
