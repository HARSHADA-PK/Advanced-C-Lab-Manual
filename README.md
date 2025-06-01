# Advanced-C-Lab-Manual
C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
# Aim: 
To write a C program print the lowercase English word corresponding to the number
# Algorithm:

1.Start

2.Initialize an integer variable n.

3.Input Validation

4.Switch Statement cases.

    Case 5: Print "seventy one"
    
    Case 6: Print "seventy two"
    
    Case 13: Print "seventy three...
   
    Case 13: Print "seventy nine"
   
   Default: Print "Greater than 79"
   
5.Exit the program.

# Program:
```
#include <stdio.h>

int main() {
    int n;
    scanf("%d", &n);
    if (n >= 71 && n <= 79) {
        switch(n) {
            case 71: printf("seventy one\n"); break;
            case 72: printf("seventy two\n"); break;
            case 73: printf("seventy three\n"); break;
            case 74: printf("seventy four\n"); break;
            case 75: printf("seventy five\n"); break;
            case 76: printf("seventy six\n"); break;
            case 77: printf("seventy seven\n"); break;
            case 78: printf("seventy eight\n"); break;
            case 79: printf("seventy nine\n"); break;
        }
    } else if (n > 79) {
        printf("Greater than 79\n");
    }

    return 0;
}

```

# Output:
![image](https://github.com/user-attachments/assets/027c868e-b821-4975-ba6d-612c5b72eb86)




Result: Thus, the program is verified successfully

# EXP NO:7 
C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 9 . 
# Aim: 
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9. 
# Algorithm:

1.Start

2.Declare char array a[50] outer loop for each digit from 0 to 9

3.Initialize counter c to 0

4.For each character in the string print count c for current digit, followed by a space

5.Increment h to move to the next digit

6.End
# Program:
```
#include<stdio.h>
int main()
{
    char str[1000];
    int freq[10]={0};
    scanf("%s",str);
    for(int i=0;str[i]!='\0';i++)
    {
        if(str[i]>='0' && str[i]<='9')
        {
            freq[str[i]-'0']++;
        }
    }
    for(int i=0;i<10;i++)
    {
        printf("%d ",freq[i]);
    }
    printf("\n");
}
```

# Output:
![image](https://github.com/user-attachments/assets/255be834-3683-49c3-acbb-361742e56e97)


Result: Thus, the program is verified successfully

# EXP NO:8 
C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
# Aim: 
To write a C program to print all of its permutations in strict lexicographical order.

# Algorithm:

1.Start

2.Declare variables s (pointer to an array of strings) and n (number of strings)

3.Memory Allocation Dynamically allocate memory for s to store an array of strings

4.Input Read the number of strings n from the user Dynamically allocate memory for each string in s

Permutation Generation Loop

5.Memory Deallocation Free the memory allocated for each string in s Free the memory allocated for s

6.End

# Program:
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

void reverse(char **arr, int start, int end) {
    while (start < end) {
        swap(&arr[start], &arr[end]);
        start++;
        end--;
    }
}

int next_permutation(char **arr, int n) {
    int i = n - 2;
    while (i >= 0 && strcmp(arr[i], arr[i + 1]) >= 0) {
        i--;
    }
    if (i < 0) return 0;

    int j = n - 1;
    while (strcmp(arr[i], arr[j]) >= 0) {
        j--;
    }
    swap(&arr[i], &arr[j]);
    reverse(arr, i + 1, n - 1);
    return 1;
}

void print_permutations(char **arr, int n) {
    qsort(arr, n, sizeof(char *), compare);
    do {
        for (int i = 0; i < n; i++) {
            printf("%s ", arr[i]);
        }
        printf("\n");
    } while (next_permutation(arr, n));
}

int main() {
    int n;
    scanf("%d", &n);
    char **arr = (char **)malloc(n * sizeof(char *));
    for (int i = 0; i < n; i++) {
        arr[i] = (char *)malloc(100 * sizeof(char));
        scanf("%s", arr[i]);
    }
    print_permutations(arr, n);
    for (int i = 0; i < n; i++) {
        free(arr[i]);
    }
    free(arr);
    return 0;
}

```

# Output:

![image](https://github.com/user-attachments/assets/cf67574c-0437-4fe8-a2ac-c0e04e8cde0c)


Result: Thus, the program is verified successfully

# EXP NO:9 
C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW. 
# Aim: 
To write a C program to print a pattern of numbers from 1 to n as shown below.
# Algorithm:

1.Start

2.Declare integer variables n, i, j, min

3.Read the value of n from the user

4.Calculate the length of the side of the square matrix: len = n * 2 - 1

5.Matrix Generation Loop

6.Calculate min as the minimum distance to the borders

7.End

# Program:
```
#include <stdio.h>
#include <stdlib.h>

void printNumberPattern(int n) {
    int size = 2 * n - 1;

    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            int num = (abs(n - 1 - i) > abs(n - 1 - j)) ? abs(n - 1 - i) : abs(n - 1 - j);
            printf("%d ", num + 1);
        }
        printf("\n");
    }
}

int main() {
    int n;
    scanf("%d", &n);
    printNumberPattern(n);

    return 0;
}

```

# Output:
![image](https://github.com/user-attachments/assets/d76a63f1-80e0-45a2-90b7-b82353c444f2)


Result: Thus, the program is verified successfully

# EXP NO:10 
C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

# Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

# Algorithm:

1.Start.

2.Define a function square() with no parameters. This function will return an integer value.

3.Inside the function: o Declare an integer variable to store the number. o Ask the user to input a number. o Calculate the square of the number (multiply the number by itself). o Return the squared value.
In the main function: o Call the square() function and display the result.

4.End.

# Program:
```
#include<stdio.h>
void square();
int main()
{
    square();
    return 0;
)
void square()
{
     int a;
     scanf("%d",&a);
     float ans=a*a;
     printf("The square of %d is : ",a,ans);
}
```

# Output:
![image](https://github.com/user-attachments/assets/b69d915f-191b-40e7-8ba7-48929124c370)


Result: Thus, the program is verified successfully
