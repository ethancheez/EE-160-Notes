# Lab 8
Try to finish by the end of lab next week, 10/20

## Task
- Copy the makefile from ~ee160/Code.lect/Roman to your Lab8 directory
- Type `make links`
- Files to Edit: (you will have to unlink these files, can just create a new file and copy paste code)
  - myreadcmd.c
  - roman.c
  - driver.c
  
## roman (roman.c, driver.c)
- Ignore leading spaces and tabs
- is_roman() should return "0" if invalid roman number
- driver.c should print error message for invalid roman numbers

Example Output:
```
Enter an number in roman numerals(EOF to quit):     m
The number is 1000

Enter an number in roman numerals(EOF to quit): v
The number is 5

Enter an number in roman numerals(EOF to quit): p
ERROR: Invalid Roman Number

Enter an number in roman numerals(EOF to quit): mvii
The number is 1007

Enter an number in roman numerals(EOF to quit): [CTRL+D]
```

## myreadcmd.c
- Ignore leading spaces and tabs
- Will only read first letter in a command, other letters will be ignored
- Commands can be separated by a semicolon ";"


Example Outputs: make sure user input is continuous until a [CTRL+D] is inputted.
```
a
The command is: a
```
```
  b      
The command is: b
```
```
        c
The command is: c
```
```
1
Error: 1 is not a letter.
```
```

Error: missing command
```
```
;
Error: missing command
```
```
a       ; b
The command is: a
The command is: b
```
```
c ; ; ; d ; e
The command is: c
Error: missing command
Error: missing command
The command is: d
The command is: e
```
```
asdjkhfkahdjaadadmackan hi
The command is: a
```
```
hvasdakdkjad ; oiqweqwidnadsnakd
The command is: h
The command is: o
```
```
[CTRL+D]
... Exiting Program ...
```

## Files to Submit
| .c Files | .h Files |
| :---: | :---: |
| roman.c | roman.h |
| romanutil.c | romanutil.h |
| | chrutil.h |
| | tfdef.h |
| driver.c | |
| myreadcmd.c | |

and your makefile...

# Submission
```bash
grade -lab8s1,ee160  *.c *.h makefile
```
