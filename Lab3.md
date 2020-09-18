# Lab 3
We assume that the user times a number. Don't worry about error checking.

Example, if you are asking for time, you don't need to worry that the user will type "five" as an input. 

Fix all warnings.

## Data Types you will probably use someday
```
%c  ->  single character
%d  ->  integer
$f  ->  float (decimals)
%s  ->  string (words, sentences)
```

### Data Type Examples
```c
    float distance, time;

    // Correct
    printf("An object falling %f feet in %f seconds ", distance, time);

    // Wrong (Not enough variables)
    printf("An object falling %f feet in %f seconds ", distance);

    // Wrong (Data type)
    printf("An object falling %d feet in %d seconds ", distance, time);
```

### %f
```
  Given: %7.2f
    - The .2 means that it will print 2 decimal places
    - The 7 means that the float printed must be at least 7 characters long
      If it is less than 7, print empty spaces in front until there is 7

  float x = 1.5;
  %.3f:		1.500
  %.2f:		1.50
  %2.2f:	1.50
  %4.2f: 	1.50
  %5.2f:	_1.50
  %7.2f:	_ _ _1.50

  Notes: 
    - Every digit is considered a character.
    - The "." also counts as one character.
    - The "_" indicates a space character.
```

## scanf

``` c
%data_type: %f, %d, %c, etc. (read above)
&variable_name

scanf("%f", &time);
```

```c
scanf("%f\n", &time);

It will scanf ("%s\n", &time) it will scan for time followed by optional white space
```

## Gravity.c

In case you need a Gravity.c fixed from Lab 2. (You can just re-use your gravity.c code)
```c
#include <stdio.h>

int main(){  

        float velocity, distance, time;

        /*  set the time  */
        time = 10;

        /*  compute the velocity */
        velocity = 32.0 * time;

        /*  compute the distance  */
        distance = (32 * time * time) / 2;

        /*  print the result  */
        printf("An object falling %4.2f feet in %4.2f seconds ", distance, time);
        printf("is traveling %4.2f ft/sec\n", velocity);

        return 0;
}
```

## seconds.c
Test for 3600, 7210, 3661. Any other number you want.

Hint: % (Mod operator) gets the remainder. 

```
Example:
    5 % 2 = 1 (2*2 + 1 = 5)
    4 % 2 = 0 (2*2 + 0 = 4)
```

## cars.c
```
cp ~ee160/Labs/Lab3/cars.c cars.c
```

## gas.c
Create a new file and make gas.c

## temperature.c
Create a new file and make temperature.c

## What you turn in
- gravity.c
- seconds.c
- cars.c
- gas.c
- temperature.c

# Submission
- To submit:
    ```
        grade -lab3s1,ee160 gravity.c seconds.c cars.c gas.c temperature.c
    ```
- To verify:
    ```
        grade -lab3s1,ee160
    ```
