# Lab 5

Due at the end of lab next week: Tuesday, September 29

## End of File Character
-   Written as "EOF"
-   Used to detect a [CTRL + D] input.
-   Or, as the name suggests, used to detect the end of a text file.

### Examples using EOF
```c
int main() {
    int input;

    printf("Input a number: ");

    while( scanf("%d", &input) != EOF ) {
  
        printf("You inputted: %d \n", input);
        printf("Input a number: ");
  
    }
}
```
```c
int main() {
    int flag, input;

    printf("Input a number: ");
    flag = scanf("%d", &input);
  
    while(flag != EOF) {
  
        printf("You inputted: %d \n", input);
        printf("Input a number: ");
        flag = scanf("%d", &input);
  
    }
}
```
-   We use an integer "flag" to store the number of input values that are scanned.
    -   A successful scan typically returns an integer of "1"
    -   If no input is scanned, or there was an error in the input, it returns "EOF"
-   Fun Fact: "EOF" is actually an integer of -1
    -   So technically you can do (flag != -1), but we use EOF for the sake of keeping it consistent with scanf.

Example output for program above:
```
Input a number: 1
You inputted: 1 
Input a number: 2
You inputted: 2 
Input a number: 3
You inputted: 3 
Input a number: 4
You inputted: 4 
Input a number: 10
You inputted: 10 
Input a number: [CTRL + D]
... Exiting Program ...
```

## If Statements
```c
/*  If Statement  */
if(condition 1) {
  //do something if condition 1 is true
}

/*  If-Else Statement */
if(condition 1) {
  //do something if condition 1 is true
} else {
  //do something if condition 1 is not true
}

/*  If-Else If-Else Statement */
if(condition 1) {
  //do something if condition 1 is true
} else if(condition 2) {
  //do something if condition 1 is not true AND condition 2 is true
} else {
  //do something if neither condition 1 nor condition 2 are true
}
```
Example:
```c
int a = 1;
int b = 2;

if(a == 1) {  //condition 1
  //this will run because condition 1 is true
} else if(b == 2) { //condition 2
  //this will NOT run even though condition 2 is true, because condition 1 was true.
}

if(a == 2) {  //condition 1
  //this will not run because condition 1 was false
} else if(b == 2) { //condition 2
  //this will run because condition 2 is true and condition 1 was false
} else {
  //this will not run because condition 2 was true
}

if(a == 2) {  //condition 1
  //this will not run because condition 1 was false
} else { 
  //this will run because condition 1 was false
}
```

### Operators
```c
&&  ->  "and"
||  ->  "or"

//Example
if(a && b) //If a AND b
if(a || b) //If a OR b
```

## sum.c
Edit the code below.
```c
/*      File : sum.c            *
 *      By   :                  *
 *      login:                  *
 *      team :                  *
 *      Date :                  */

/*  A program to compute the sum of numbers given on the input  */

int main()
{

        /*  Initialize the sum             */


        /*  Get the first input            */


        /*  While there is more input      */


                /*  Accumulate the sum     */


                /*  Get the next input     */


        /*  Print the results              */


}
```
Example output:
```
Enter an integer value: 1
Enter an integer value: 2
Enter an integer value: 3
Enter an integer value: 4
Enter an integer value: 5
Enter an integer value: [CTRL + D]
Sum: 15.00
```

## avg.c
Copy your sum.c code you just made, but instead of calculating the sum, calculate the average. The code should be similar.

Example output:
```
Enter an integer value: 10
Enter an integer value: 20
Enter an integer value: 30
Enter an integer value: [CTRL + D]
The average of 3 input values is 20.000000
```

## weight.c
You can copy your avg.c file you just made and edit it for weight.c

Example output:
```
Enter a weight/value pair: 20 90
Enter a weight/value pair: 30 80
Enter a weight/value pair: 50 60
Enter a weight/value pair: [CTRL + D]
The weighted average of 3 input values is 72.000000
```
The algorithm to calculate weighted average using the example inputs above:
```
   [ (20 * 90) + (30 * 80) + (50 * 60) ] / [ 20 + 30 + 50 ] = 72
```

Hint: you can scan multiple inputs at the same time
```c
scanf("%d %d", &a, &b);
```

## temptbl.c
Copy temptbl.c from your Lab 4.
-   If you think about it, you have to change very little of your lab 4 code
-   In Lab 4, the increment/decrement was set to 5.
    -   Now, there is a third parameter in the function, which is how much the temperature should increment/decrement for every loop
-   Make sure the step is not less than 0.001
-   Make sure it can account for a negative step input (see example output on class website if you don't know what this means)
-   Make sure your temptable function returns the number of lines printed
-   Example outputs are shown on the class website.

## account.c
Copy your account.c from your Lab 4.
-   Try your best not to edit the calc_acc_amount function
-   Basically, add a new scan for the compound interval (annually, monthly, or daily)
    -   Make sure you add a condition to check for valid/invalid inputs
-   Add if statements to compute the accumulated amount for each of the three possible compound interval.

You can use this website to test if your code is calculating the correct results:

https://www.thecalculatorsite.com/finance/calculators/compoundinterestcalculator.php

Website Notes:
-   Keep the interest rate setting at "yearly"
-   Change the compound interval setting to yearly/monthly/daily for testing
-   Results are printed under "Final investment value"

Example Output:
```
Enter Initial Amount (EOF to exit): 500
Enter Rate of Interest: 0.05
Enter number of years of compounding: 5
Enter compounding Annual/Monthly/Daily [-1/2/3]: -1
Accumulated Value: $638.14 

Enter Initial Amount (EOF to exit): 500
Enter Rate of Interest: 0.05
Enter number of years of compounding: 5
Enter compounding Annual/Monthly/Daily [-1/2/3]: 2
Accumulated Value: $641.68

Enter Initial Amount (EOF to exit): 500
Enter Rate of Interest: 0.05
Enter number of years of compounding: 5
Enter compounding Annual/Monthly/Daily [-1/2/3]: 3
Accumulated Value: $642.00

Enter Initial Amount (EOF to exit): [CTRL + D]
... Exiting Program ...
```

### Macros
```c
#define ANNUALLY -1
#define MONTHLY 2
#define DAILY 3
```

## What to submit
-   sum.c
-   avg.c
-   weight.c
-   temptbl.c
-   account.c

# Submissions
-   To submit your files:
```
    grade -lab5s1,ee160 sum.c avg.c weight.c temptbl.c account.c 
```
-   To verify:
```
    grade -lab5s1,ee160
```
