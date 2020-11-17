# Lab 13
Last lab!

Lab 13 will be due next week Tuesday at 10:30 AM

Lab 12 due at the end of class today


## Arrays
- Used to store several values in one variable name.
  - Instead of having several variables like num1, num2, num3, num4, etc..
  - Use an array with just the name "num" and use num[0], num[1], num[2], etc..
- Example:
```c
//Initialize an array of integers with the name "num" and size 100 (0-99)
int num[100];

for(int i = 0; i < 100; i++) {
  num[i] = i;
  *(num+i) = i; //This is another way to call the array (arrays can be pointers too!)
}

//Print the value inside the 0th index in the array
printf("1: %d \n", num[0]);
printf("2: %d \n", *(num)); //equivalent to the line above

//Print the value inside the 50th index in the array
printf("3: %d \n", num[50]);
printf("4: %d \n", *(num+50));  //equivalent to the line above
```
- Output for code above
```
1: 0 
2: 0 
3: 50
4: 50
```

## averages.c
- Functions to edit:
```c
double tableAverage(double a[], int num);

int tableMatchingElements(double a[], int num, double target);
```
- Hint: some other useful functions you can add:
```c
void printLarger(double a[], int num, double target);

void printSmaller(double a[], int num, double target);

int largerElements(double a[], int num, double target);

int smallerElements(double a[], int num, double target);
```
- Example Input/Output:
```
10 20 30 30 40 50
Average of the 6 values read is: 30.000000
There are 2 values equal to the average.
There are 2 values greater than the average:
40
50
There are 2 values less than the average:
10
20
```

## water
- Go to your Lab 13 directory and type this to copy all the files needed for this part:
```bash
cp ~ee160/Code.lect/Water/* .
```

- You only need to edit the compute_usage() function:
```c
float compute_usage(int num, int *vals, int use[], int *hi_idx);

//  int num:      number of data readings
//  int *vals:    an array that stores the meter reading data for each respective hour (from the day1 data file)
//  int use[]:    an array that stores the usage for each hour interval
//  int *hi_idx:  a pointer to an integer value that stores the index of the highest usage

//  Function returns the average usage for the day (24 hours).
```

- To execute your file:
```
./water < day1
```
- Example output: 
  - Understand how the numbers in the second column are obtained before starting the code
```
                 0:00   3  
                 1:00   151
                 2:00   4  
                 3:00   2
                 4:00   22
                 5:00   36
                 6:00   8
                 7:00   2
                 8:00   3
                 9:00   2
                10:00   0
                11:00   1
                12:00   2
                13:00   3
                14:00   1
                15:00   5
                16:00   6
                17:00   18
                18:00   5
                19:00   4
                20:00   31
                21:00   14
                22:00   2
                23:00   2


the average usage was 13.625000
the hi usage was 151 at 1:00
```

## makefile
- If you don't want to remove the example water executable, rename your executable file to "water2"
```makefile
all: averages water

averages:

water:

# dependency lines (add anything you need here)


clean:
  rm *.o
  rm averages
  rm water2
```

# Submission
- To submit:
```bash
  grade -lab13s1,ee160  *.c *.h makefile
```
- To verify:
```bash
  grade -lab13s1,ee160
```
