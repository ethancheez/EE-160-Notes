# Lab 6
Lab 5 is due on Friday 10/2 at 5 PM

Lab 6 is due next week October 6

## Header Files (.h)
- Used to store prototype functions
- Must include this inside your .c function.
```c
#include "name.h"
```

### Example 1
Remember doing this?
```c
//This is your main driver, driver.c

float test_function(int some_variable);

int main() {
  //some code
}

float test_function(int some_variable) {
  //some code
}
```
Well now you can have header files to store the prototype function.
```c
//This is a header file, header.h

//This is the only thing you need in here
float test_function(int some_variable);
```
Now in your driver.c,
```c
#include "header.h"

int main() {
  //some code
}

/* Even though there is no prototype inside this driver.c file, because you included the header.h file at the very beginning,
 * this driver file can read the prototype inside header.h and therefore this function will work.
 */
float test_function(int some_variable) {
  //some code
}
```

### Example 2
Let's take this up a notch. Header files can be powerful to keep your driver file clean and to save time.

- header.h
```c
float test_function(int some_variable);
```

- header.c
```c
#include <stdio.h>

float test_function(int some_variable) {
  printf("The header.c file was accessed \n");
  return some_variable + 1;
}
```

- driver.c
```c
#include <stdio.h>
#include "header.h"

int main() {
  float output = test_function(2);
  printf("The output is: %.2f \n", output);
}
```

As you can see, the driver function only contains a main() function.

This is useful because now you can reuse the test_function() function in any driver file (driver1.c, driver2.c, etc.) without having to copy paste the function muiltiple times. You just have to import the header.h file using #include

### Compiling multiple files
- Using Example 2 above, you can compile all those files by typing:
```bash
cc driver.c header.c
```
- The output:
```
The header.c file was accessed 
The output is: 3.00
```


## #ifdef DEBUG
Remember defining macros for lab 5 in your account.c file? This is very similar.

```c
#include <stdio.h>

// This is where you define the macro for "DEBUG"
#define DEBUG

//#define DEBUG2

int main() {
  // This is very similar to a basic if statement
  #ifdef DEBUG  // "If DEBUG is defined"
    printf("DEBUG is defined \n");
  #endif  // Basically a closing bracket
  
  // This will not run because DEBUG2 is not defined (it is commented out)
  #ifdef DEBUG2
    printf("DEBUG2 is defined \n");
  #endif
}
```

## In Lab Notes/Questions
- Something interesting I found... modulus (%) only works for integers. Make sure that user input is set to an integer and not a float.
```c
float input = 2.78131;
//this will NOT work
input % 2
```

## numbers.c
- Hint: You may need a whole lot of variables...
- You need to calculate the TOTAL NUMBER and SUM of the following:
  - Positive numbers
  - Negative numbers
  - Even numbers
  - Odd numbers
  - Positive even numbers
  - Negative odd numbers
  - All numbers
- Yes, it's possible to do all this with three If-Else statements (but you're not forced to do it this way, do it the way that's most comfortable for you)
- The program exits when you enter "0"

## driver1
- You need files:
  - driver1.c
  - maxmin.c
  - maxmin.h
  
Example Output:
```
Enter a pair of floats (CTRL+D to exit): 10 20
The larger of the two values is: 20.00
The smaller of the two values is: 10.00
Enter a pair of floats (CTRL+D to exit): 1.5 1.4   
The larger of the two values is: 1.50
The smaller of the two values is: 1.40
Enter a pair of floats (CTRL+D to exit): 1 1
The larger of the two values is: 1.00
The smaller of the two values is: 1.00
Enter a pair of floats (CTRL+D to exit): [CTRL + D]
... Exiting Program ...
```

## driver2
- You need files:
  - driver2.c
  - maxmin.c
  - maxmin.h
  
Example Output (with DEBUG statements enabled):
```
Enter a number: 23.5
== DEBUG == Current Highest: 23.50       Current Lowest: 23.50
Enter a number: 16.1
== DEBUG == Current Highest: 23.50       Current Lowest: 16.10
Enter a number: -35.2
== DEBUG == Current Highest: 23.50       Current Lowest: -35.20
Enter a number: 90
== DEBUG == Current Highest: 90.00       Current Lowest: -35.20
Enter a number: -13.1
== DEBUG == Current Highest: 90.00       Current Lowest: -35.20
Enter a number: 0
== DEBUG == Current Highest: 90.00       Current Lowest: -35.20
Enter a number:

Highest: 90.00
Lowest:  -35.20 
```

## driver3
- You need files:
  - driver3.c
  - exponent.c
  - exponent.h
- I'm not going to require you to put debug statements here, but if your code doesn't work as intended, put debug statements in.
  
Example Outputs:
```
Enter a base and exponenet: 6 8
Result = 1679616.00
```
```
Enter a base and exponenet: 6 0
Result = 1.00 
```
```
Enter a base and exponenet: 6 -1
Result = 0.00
```


## What to Submit
- driver1.c
- driver2.c
- driver3.c
- exponent.c
- exponent.h
- maxmin.c
- maxmin.h
- numbers.c

# Submission
- To Submit:
```bash
  grade -lab6s1,ee160  *.c *.h
```
- To Verify:
```bash
  grade -lab6s1,ee160
```
