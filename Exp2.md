# EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
## Aim:
To write a C program for passing structure as function and returning a structure from a function

## Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
## Program:
```c
#include<stdio.h>
struct numbers
{
   int a;
   int b;
}n;
int add(struct numbers n);
int main()
{
   scanf("%d %d ",&n.a,&n.b);
   printf("%d",add(n));
}
int add(struct numbers n)
{
    return n.a+n.b;
}

```
## Output:
![image](https://github.com/user-attachments/assets/a912c4e0-a539-4abb-b75d-ac5b2e7e9fe8)

## Result:
Thus, the program is verified successfully
