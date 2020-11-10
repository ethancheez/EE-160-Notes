# Lab 12
Lab 10 due at the end of lab today.

Lab 12 due next week.

## Pointers and References
&: Referencing the Address

*: Pointers for Dereferencing


## swap.c swaptest.c
<p align="center">
  <img src="https://i.gyazo.com/5917eebaf64ce34c31068931f623808f.png" />
</p>

- swap( &a, &b );
  - The '&' means it is creating references to the address for the variables 'a' and 'b'

<p align="center">
  <img src="https://i.gyazo.com/66d5d4b5892bd83a448d0063b2c89eba.png" />
</p>

- float temp;
  - This creates the variable 'temp' local to the swap function.
- Note that the variables 'a', 'b', and 'c' are local to swaptest.c and swap.c cannot access these variables. This is why pointers are useful so you are able to access these variables in other functions, which is how swap(&a,&b) is able to access variables 'a' and 'b'

<p align="center">
  <img src="https://i.gyazo.com/9d9925d40c7540754a293bb5109be13b.png" />
</p>

- temp = \*a;
  - 'a' is a reference, which is an address. In order to read the actual value stored in memory (the number 2.5), we need to dereference it by using '\*'
  - '\*a' is used to dereference and read the value 2.5 and store it into 'temp'

<p align="center">
  <img src="https://i.gyazo.com/fa701af8eb9e622fceb35b77d45af8c1.png" />
</p>

- \*a = \*b;
  - Again, 'a' and 'b' are references. So we need to derefence them in order to read and change the values stored in memory.
  - 5.9 from variable 'b' is stored into variable 'a'

<p align="center">
  <img src="https://i.gyazo.com/4de8750102899b10ec8254e9e43ec687.png" />
</p>

- \*b = temp;
  - temp is local to swap and is not a pointer so we don't need any pointers or dereferences.
  - 'b', however, is a reference so we need to dereference it.
  - 2.5 from variable 'temp' is stored into variable 'b'


## swapbig.c
- Given two float inputs a and b, swap the values (if necessary) so that a <= b.
```c
  void swap_big(float *a, float *b);
```
- Create a data file "swapbig.dat" to test the swap_big function for all possible conditions.
- Also create a driver file to test your swap_big function.
- This program should utlize the swap function.
- Test your program with:
```bash
  ./swapbig < swapbig.dat
```

## reorder.c
- Given three float inputs a, b, and c, swap the values (if necessary) so that a <= b <= c.
```c
  void reorder(float *a, float *b, float *c);
```
- Create a data file "reorder.dat" to test the reorder function for all possible conditions.
- Also create a driver file to test your reorder function.
- This program should utilize the swap_big function.
- Test your program with:
```bash
  ./reorder < reorder.dat
```

## makefile
- Please make it so the executable files are "./swap", "./swapbig", and "./reorder" (NOT ./a.out) to make grading easier. Thanks :)

# Submission
- To grade:
```bash
  grade -lab12s1,ee160  *.c *.h *.dat  makefile
```
- To verify:
```bash
  grade -lab12s1,ee160
```
