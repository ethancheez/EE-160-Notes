# Lab 11 (OPTIONAL - Extra Credit)
Due by December 11

## Taylor Series for cosine
<p align="center">
  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRtLAvb6k6l9-QL7AVBN-Ei1gBXX6ZqsoLfXA&usqp=CAU" />
</p>

- You have to basically code this series above to compute for cos(x).


## Tips
I suggest using "long double" instead of "double" or "float" for large numbers
- "long double" is an 80-bit number.
- "double" is a 64-bit number.
- "float" is a 32-bit number.

Put debug statements to figure out which variables you should change to "long double"... or just change everything

Here is a reference to all the C data types: https://en.wikipedia.org/wiki/C_data_types


## Functions Needed/Recommended:
- exponent.h
```c
double pos_power(float base, int exponenet);
```
- util.h
```c
long double factorial(int n);

int close_enough(long double a, long double b);
```
- trig.h
```c
double cosine(float x);
```


## makefile
- makefile template, complete this.
```makefile
# makefile for Lab 11

# target to create all executables for this lab
all: trig

#complete the dependency and action lines for the following targets

# Problem 2 - cos()
trig: 

# source file dependencies
#  You should fill these in and add any additional targets you need

driver1.o: 

trig.o: 

util.o:


# utility targets

clean:
  rm  -f *.o
        
real_clean: clean
  rm  -f trig a.out core
```


## Example Input/Output
```
Enter an angle in radians:  0
cos(0.000000) = 1.000000    

Enter an angle in radians:  1
cos(1.000000) = 0.540303    

Enter an angle in radians:  10
cos(10.000000) = -0.839072  

Enter an angle in radians:  1.570796327
cos(1.570796) = -0.000001   

Enter an angle in radians:  1000
cos(1000.000000) = 0.563141 

Enter an angle in radians:  -2000
cos(-2000.000000) = -0.363962 

Enter an angle in radians:  3.1415926535897
cos(3.141593) = -1.000000   

Enter an angle in radians:  [CTRL+D]
```

# Submission
- To grade:
```bash
  grade -lab11s1,ee160  *.c *.h  makefile
```
- To verify: 
```bash
  grade -lab11s1,ee160
```
