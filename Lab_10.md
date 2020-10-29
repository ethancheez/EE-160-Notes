# Lab 10
Lab 9 due at the end of lab today

Lab 10 will be due next week 

## For Loops
Here is something we are familiar with:
```c
int num = 0;
while(num < 10) {
  //some code
  num++;
}
```

Now, we can use for loops which has the same concept as a while loop but can be more useful in several ways.

Here is the general format of a for loop:
```
for( [variable declaration/initialization] ; [condition that will keep the loop running when this is true] ; [increment after each loop iteration] ) {
  //some code
}
```

Now using the while loop example above, converting it to a for loop gives:
```c
for(int num = 0; num < 10; num++) {
  //some code
}
```
- This looks cleaner! There are fewer lines compared to a while loop.


## Possibilities with a For Loop
- You are not required to have something inside each of the parameters inside the for loop.

### Infinite Loops
1. You can have:
```c
for(;;) {
  //some code
}
```
This is equivalent to:
```c
while(1) {
  //some code
}
```

2. You can have: 
```c
for(int num = 0; ; num++) {
  //some code
}
```
This is equivalent to:
```c
int num = 0;
while(1) {
  //some code
  num++;
}
```

### No Initializations (initialized outside of for loop)
1. You can have:
```c
int num = 0;
for(; num < 10; num += 2) {
  //some code
}
```
This is equivalent to:
```c
int num = 0;
while( num < 10 ) {
  //some code
  num += 2;
}
```

## counters2.c
Copy this code and change ALL the while loops to for loops:
```c
/*      File : counters2.c       *
 *      By   :                  *
 *      login:                  *
 *      team :                  *
 *      Date :                  */

/*
 * A set of counting functions written using while loops.
 */

#include <stdio.h>

void count_up(int n);
void count_down(int n);
void count_some(int start, int finish, int incr);

int main()
{
        count_up(10);            /* count up from 1 to 10  */
        count_down(10);          /* count down from 10 to 1 */
        count_some(5, 15, 3);    /* count from 5 to 15 by 3 */
        count_some(15, 5, -3);   /* count from 15 to 5 by -3 */

}

void count_up(int n)
{
  int i;

        i = 1;
        while (i <= n)
        { 
                printf("%d\n", i);
                i++;
        }
}

void count_down(int n)
{
  int i;

        i = n;
        while (i >= 1)
        { 
                printf("%d\n", i);
                i--;
        }
}

void count_some(int start, int finish, int incr)
{
        if (incr == 0)
                return;           /* do nothing if no increment */

        if (incr > 0)       /* count up */
                while (start <= finish)
                { 
                        printf("%d\n", start);
                        start += incr;
                }
        else                /* count down */
                while (start >= finish)
                { 
                        printf("%d\n", start);
                        start += incr;
                }
}
```
This should be the output:
```
1
2
3
4
5
6
7
8
9
10
10
9
8
7
6
5
4
3
2
1
5
8
11
14
15
12
9
6
```

## avg.c 
Copy this code and change ALL the for loops to while loops:
```c
/*      File : avg.c            *
 *      By   :                  *
 *      login:                  *
 *      team :                  *
 *      Date :                  */

/*
 * Compute average of its input values.
 */

#include <stdio.h>

int main()
{
  int          next;               /* next input value */
  long         sum;                /* running total */
  unsigned int n;                  /* number of input values */
  int          result;             /* did we read another value? */
  double       avg;                /* average of input values */

        for (sum = n = 0; (result = scanf("%d", &next)) == 1; n++)
                sum += next;   
        if (result != EOF)
                printf("Warning: bad input after reading %u values\n", n);
        printf("Average of %u values is %f.\n", n, (n == 0) ? 0.0 : (double) sum / n);
  
}
```
- If you're curious what this line means (you don't have to change this line):
```c
  (n == 0) ? 0.0 : (double) sum / n
```
- This is equivalent to:
```c
if(n == 0)
  return 0.0;
else
  return (double) sum / n;
```
- This is basically just checking to make sure it is not dividing by 0. If it is, it just returns 0.

Example Outputs:
```
10 20 30 40 50
[CTRL + D]
Average of 5 values is 30.000000.
```
```
10 20 30 40 lol 50
Warning: bad input after reading 4 values
Average of 4 values is 25.000000.
```

## questions.c
- Here is the tfdef.h file if you can't find it (also added stuff for you guys :D):
```c
// tfdef.h
#define TRUE 1
#define FALSE 0

#define IS_LOWER(c) ((c) >= 'a' && (c) <= 'z')

#define tolower(c) (IS_LOWER(c) ? c : c - 'A' + 'a')
```

Copy this code and change ALL the for loops to while loops:
```c
/*      File : questions.c      *
 *      By   :                  *
 *      login:                  *
 *      team :                  *
 *      Date :                  */

/*
 * Ask the user a question.
 */
#include <stdio.h>
#include "tfdef.h"

int main()
{
        printf("Don't you just love this class? ");
        if (yesOrNo())
                printf("YES!  We knew it.\n");
        else
                printf("NO?  Come on, you know you love this class.\n");
  
}

int yesOrNo(void)
{
  int answer;                        /* holds input character */
  int c;

        for (;;)
        {
                /* process each input line */

                c = getchar();
                if ((answer = tolower(c)) == EOF)
                        return FALSE;                  /* EOF is NO! */

                /* read characters until the end of the line */
                for (; c != '\n' && c != EOF; c = getchar());

                /* return an appropriate value for Yes or No */
                if (answer == 'y')
                        return TRUE;
                if (answer == 'n')
                        return FALSE;

                /* error message if there's a problem */
                printf("Please answer with a YES or NO: ");
        }
}
```


Example Outputs:
```
Don't you just love this class? a
Please answer with a YES or NO: b
Please answer with a YES or NO: 1
Please answer with a YES or NO: y 
YES!  We knew it.
```
```
Don't you just love this class? YES   
YES!  We knew it.
```
```
Don't you just love this class? nOOOoooOOOOOOOO
NO?  Come on, you know you love this class.
```


## averager.c
Edit this code so it will produce the correct outputs:
```c
/*      File : averager.c       *
 *      By   :                  *
 *      login:                  *
 *      team :                  *
 *      Date :                  */

/*
 * Read in a number of values to read and then print the average
 * of those values.
 */

#include <stdio.h>

int main()
{
  int expected;
  int count;
  double sum;
  int value;

        while (scanf("%d", &expected) != EOF)
        {
                sum = 0;
                for (count = 0; count < expected; count++)
                {
                        scanf("%d", &value);
                        sum += value;
                }
                printf("Average of %d values is %.2f\n",
                       count, count != 0 ? sum / count : 0.0);
        }
  
}
```
- Note: the program should just EXIT after an invalid input was detected.

Example Outputs:
```
5
10 20 30 40 50
Average of 5 values is 30.00
7
15 20 40 50 60 40 50
Average of 7 values is 39.29
[CTRL + D]
```
```
5
10 20 30 40 50
Average of 5 values is 30.00
Lol I am typing a valid input in. Jk this isn't valid.
Error!  Can't read number of expected values.
```
```
5
10 20 30 40 50
Average of 5 values is 30.00
6
50 70 Happy Halloween 40 60
Error!  Can't read expected value #2.
Average of 2 values is 60.00
```

## Files to Submit
- counters2.c
- avg.c
- questions.c
- averager.c
- tfdef.h


# Submission
- To submit:
```bash
  grade -lab10s1,ee160  *.c *.h 
```
- To verify:
```bash
  grade -lab10s1,ee160
```
