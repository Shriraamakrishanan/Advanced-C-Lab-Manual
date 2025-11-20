# EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
## Program:
```c
#include<stdio.h>
struct eligib
{
   int age;
   char n[4];
};
int main()
{
   struct eligib e;
   scanf("%d%s",&e.age,e.n);
   if(e.age<=6)
   {
     printf("Age:%d\nName:%svaccine:%d\neligibility:no",e.age,e.n,e.age);
   }
  else
  {
     printf("Age:%d\nName:%svaccine:%d\neligibility:yes",e.age,e.n,e.age);
  }
}
```


## Output:

![image](https://github.com/user-attachments/assets/2cfad7f9-a3fb-4df1-a7df-1c7224f0af48)



## Result:
Thus, the program is verified successfully. 
