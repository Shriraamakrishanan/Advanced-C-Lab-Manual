# Advanced-C-Lab-Manual

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


 
# EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

## Aim:
To write a C program to read a file name from user

## Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
## Program:
```c
#include <stdio.h>
int main()
{
   FILE *p;
   char name[30];
   scanf("%s",name);
   printf("%s File Created Successfully",name);
   p=fopen("name","w");
   printf("\n%s File Opened",name);
   fclose(p);
   printf("\n%s File Closed",name);
}
```
## Output:
![image](https://github.com/user-attachments/assets/6e96db95-3c76-4990-90a1-eb450b7d17b3)

## Result:
Thus, the program is verified successfully
 


# EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
## Aim:
To write a C program to read, a file and insert text in that file
## Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
## Program:
```c
#include <stdio.h>
int main()
{
   FILE *p;
   char name[20];
   int num;
   char text[50];
   scanf("%s%d",name,&num);
   p=fopen("name","w");
   printf("%s Opened",name);
   for(int i=0;i<num;i++)
   {
      scanf("%s",text);
      fputs(text,p);
   }
   printf("\nData added Successfully");

}
```
## Output:

![image](https://github.com/user-attachments/assets/3baf2414-bb13-4a8a-81c9-cd5792311b62)

## Result:
Thus, the program is verified successfully



# Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

## Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

## Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Subject
{
    char name[20];
    int marks;
};
int main()
{
    int i,n;
    scanf("%d",&n);
    struct Subject *s = (struct Subject *)malloc(n*sizeof(struct Subject));
    if(s==NULL)
    {
        printf("Memory Alocation Failed\n");
        return 1;
    }
    for(i=0;i<n;i++)
    {
        scanf("%s %d",s[i].name,&s[i].marks);
    }
    for(i=0;i<n;i++)
    {
        printf("%s  %d\n",s[i].name,s[i].marks);
    }
    free (s);
    return 0;
}
```
## Output:

![image](https://github.com/user-attachments/assets/e9c8ca61-aa99-49be-a68a-56c21bdd0829)

## Result:
Thus, the program is verified successfully

# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
## Aim:
To write a C program print the lowercase English word corresponding to the number
## Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
## Program:
```c
#include<stdio.h>
#include<math.h>
int main()
{
    int n;
    scanf("%d",&n);
    if(n>=1 && n<=pow(4,3))
    {
      switch(n)
      {
        case 5:
        {
           printf("seventy one");
           break;
        }
        case 6:
        {
            printf("seventy two");
            break;
        }
        case 13:
        {
            printf("seventy three");
            break;
        }
        case 14:
        {
           printf("seventy four");
           break;
        }
        case 15:
        {
           printf("seventy five");
           break;
        }
        case 16:
        {
            printf("seventy six");
            break;
        }
        case 5:
        {
             printf("seventy seven");
             break;
        }
        case 6:
        {
             printf("seventy eight");
             break;
        }
        case 13:
        {
             printf("seventy nine");
             break;
        }
        default:
        {
            printf("Greater than 13");
        }
      }
   }
}
```
## Output:
![image](https://github.com/user-attachments/assets/1bb68404-0d25-41d1-a72a-70ee82c40922)

## Result:
Thus, the program is verified successfully
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:

```c
#include<stdio.h>
#include<string.h>
int main()
{
   char a[50];
   scanf("%s",a);
   int l=strlen(a);
   char h='0';
   for(int i=0;i<4;i++)
   {
      int c=0;
      for(int j=0;j<l;j++)
      {
         if(a[j]==h)
         {
         c+=1;
         }
      }
      printf("%d ",c); h++;
    }
}
```

## Output:
![image](https://github.com/user-attachments/assets/6fbcdc7f-49ef-4fcc-8cb1-8390fc66fac1)

## Result:
Thus, the program is verified successfully

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
## Program:
```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
int next_per(int n, char **s)
{
     for(int i = n - 1 ; i > 0 ; i--) if(strcmp(s[i],s[i-1]) > 0)
     {
       int j=i+1;
       for(;j<n;j++)
         if (strcmp(s[j],s[i-1])<=0)
         break;
         char *t=s[i-1];
         s[i-1]=s[j-1];
         s[j-1]=t;
         for(;i<n-1;i++,n--)
         {
             t=s[i];
             s[i]=s[n-1];
             s[n-1]=t;
         }
         return 1;
     }
     for(int i=0;i<n-1;i++,n--)
     {
         char *t=s[i];
         s[i]=s[n-1];
         s[n-1]=t;
     }
     return 0;
}
int main()
{
    char **s;
    int n;
    scanf("%d",&n);
    s=calloc(n,sizeof(char*));
    for(int i=0;i<n;i++)
    {
       s[i]=calloc(n,sizeof(char*)*5);
       scanf("%s",s[i]);
    }
    do
    {
       for(int i=0;i<n;i++)
         printf("%s%c",s[i],i==n-1?'\n':' ');
    }
    while(next_per(n,s));
    {
        for(int i=0;i<n;i++)
          free (s[i]);
        free(s);
        return 0;
     }
}
```
## Output:

![image](https://github.com/user-attachments/assets/456c6190-4a1c-4e68-a99d-5ef89a2f5ce4)


## Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.
## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:
```c
#include<stdio.h> 
int main()
{
   int n,i,j,min; 
   scanf("%d",&n);
   int len=n*2-1; 
   for (i=0;i<len;i++)
   {
      for (j=0;j<len;j++)
      {
         min=i<j?i:j;
         min=min<len-i-1?min:len-1-i; 
         min=min<len-j-1?min:len-1-j; 
         printf("%d ",n-min);
      }
      printf("\n");
   }
   return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/dc62f770-2189-4d8f-8de7-623ca384a25a)

## Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

## Program:

```c
#include <stdio.h>
void square();
int main()
{
    square();
    return 0;
}
void square()
{
    int a;
    scanf("%d",&a);
    float ans = a*a;
    printf("The square of %d is : %.2f",a,ans);
}
```
## Output:
![image](https://github.com/user-attachments/assets/f37e6ef6-d50a-4c34-ac3c-a210493cf86f)

## Result:
Thus, the program is verified successfully

# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```c
int stack[40],top,i;
void display()
{
   for(i=top;i>=0;i--)
   {
      printf("%d\n",stack[i]);
   }
}
```
## Output:

![image](https://github.com/user-attachments/assets/2d2dc82c-9928-4f8f-a07c-9a4c31f67028)

## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```c
int size=3,top=1;
float stack[40];
void push (float data)
{
   if (top==size-1 )
   {
      printf("stack is full\n");
   }
   else
   {
      top ++;
      stack[top] = data;
   }
}
```


## Output:

![image](https://github.com/user-attachments/assets/ebcbb468-1e9b-4f3d-903b-9156c1269bb2)
## Result:
Thus, the program to push the given element in to a stack using array is verified successfully

# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```c
int queue[50], rear, front,i;
void display()
{
   if(front==-1)
   {
      printf("No elements to display");
   }
   else
   {
     for(i=front;i<=rear;i++)
     {
       printf("%d ",queue[i]);
     }
   }
}
```

## Output:

![image](https://github.com/user-attachments/assets/2d892bf2-90fc-4fd4-95ee-0c6cfcfa51e5)

## Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```c
int size=4, rear=-1, front=-1;
float queue[50];
void enqueue(float data)
{
   if(rear<size)
   {
     if(front==-1)
     {
        front=0;
     }
     rear=rear+1;
     queue[rear]=data;
    }
}
```

## Output:

![image](https://github.com/user-attachments/assets/7bc7dc0b-c050-4d3f-ac75-6cdc64c2fbd3)


## Result:
Thus, the program to insert elements in queue using array is verified successfully.
 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.
## Program:
```c
int front, rear;
void dequeue()
{
    if(front==-1&&rear==-1)
    printf("Queue Underflow.");
    else if(front==rear)
    front=rear=-1;
    else
    {
        front=front+1;
    }
}
```

## Output:

![image](https://github.com/user-attachments/assets/5de5ee70-9217-4f6a-b3cd-7f800bafd855)

## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.


# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:
```c
struct Node
{
   struct Node *next;
   char data;
}*head;
void search(char data)
{
   struct Node *ptr;
   char item=data;
   int i=0,flag;
   ptr = head;
   if(ptr == NULL)
   {
     printf("Empty List\n");
   }
   else
   {
     while (ptr!=NULL)
     {
       if(ptr->data == item)
       {
          printf("item %c found at location %d ",item,i+1); flag=0;
       }
       i++;
       ptr = ptr -> next;
     }
     if(flag!=0)
     {
        printf("Item not found\n");
     }
   }
}
```

## Output:

![image](https://github.com/user-attachments/assets/1b0d14ef-1328-4ed5-8587-4fc0543643be)

## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
## Aim:
To write a C program to insert a node in a linked list.
## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:

```c
struct Node
{
   char data;
   struct Node *next;
}*head;

void insert(char data)
{
    struct Node n=(struct Node)malloc(sizeof(struct Node));
    struct Node *temp;
    if(head==NULL)
    {
       head=n;
       n->data=data;
       n->next=NULL;
       temp=head;
       return;
    }
    while(temp->next!=NULL)
    {
       temp=temp->next;
    }
    n->data=data;
    n->next=NULL;
    temp->next=n;
}
```

## Output:

![image](https://github.com/user-attachments/assets/91711b1c-9d2c-4c7e-881e-b77e162ccee7)

## Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:

```c
struct Node
{
   struct Node *prev;
   struct Node *next;
   int data;
}*head;
void display()
{
   struct Node *temp;
   temp=head;
   while(temp!=0)
   {
      printf("%d ",temp->data); temp=temp->next;
   }
}
```

## Output:

![image](https://github.com/user-attachments/assets/ae534c20-d3a9-4b78-8f70-dec5a58da57e)

## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:
```c
struct Node
{
   struct Node *prev;
   struct Node *next;
   float data;
}*head;
void insert(float data)
{
    struct Node n=(struct Node)malloc(sizeof(struct Node));
    struct Node *temp;
    if(head==NULL)
    {
       head=n;
       n->data=data;
       n->next=NULL;
       n->prev=NULL;
       temp=head;
    }
    else
    {
       while(temp->next!=NULL)
       {
          temp=temp->next;
       }
       n->data=data;
       n->next=NULL;
       n->prev=temp;
       temp->next=n;
     }
}
```

## Output:

![image](https://github.com/user-attachments/assets/116e3895-a09b-437d-9d30-3cc947435780)

## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.


# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


## Program:

```c
struct Node
{
    char data; 
    struct Node *next;
}*head;
void delete()
{
    if(head==NULL)
    {
        printf("List is empty\n");
        return;
    }
    else if(head->next==NULL){
        head=NULL;
        free(head);
        printf("Node deleted from the begining ...\n");
    }
    else
    {
        struct Node *ptr;
        ptr=head;
        head=head->next;
        free(ptr);
        printf("Node deleted from the begining ...\n");
    }
}
```

## Output:

![image](https://github.com/user-attachments/assets/6ce7dec0-c6ca-48d7-a4e8-d9d2cea3b5c1)

## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.


## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```c
#include<stdio.h>
int max_of_four(int a,int b,int c,int d)
{
    if(a>b && a>c && a>d)
    {
        return a;
        
    }
    else if(b>a && b>c && b>d)
    {
        return b;
        
    }
    else if(c>a && c>b && c>d)
    {
        return c;
        
    }
    else
    {
        return d;
        
    }
    
}
int main()
{
    int n1,n2,n3,n4,greater;
    scanf("%d%d%d%d",&n1,&n2,&n3,&n4); 
    greater=max_of_four(n1,n2,n3,n4);
    printf("%d",greater);
}
```

## Output:
![437661122-98f208fd-842f-4235-88c8-781014e0532f](https://github.com/user-attachments/assets/821d0a12-9d35-4ae9-9f84-a05c9df069a1)


## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```c
#include<stdio.h>
void calculate_the_max(int n,int k)
{
    int a=0,o=0,x=0;
    for(int i=1;i<=n;i++)
    {
        for(int j=1+i;j<=n;j++)
        {
            if((i&j)>a && (i&j)<k)
            {
                a=i&j;
                
            }
            if((i|j)>o && (i|j)<k)
            {
                o=i|j;
                
            }
            if((i^j)>x && (i^j)<k)
            {
                x=i^j;
                
            }
            
        }
}
printf("%d\n%d\n%d\n",a,o,x);
}
int main()
{
    int n,k; 
    scanf("%d%d",&n,&k); 
    calculate_the_max(n,k);
}
```

## Output:
![437661306-eaf6373c-dc14-4be3-8de5-3522c6c50ef0](https://github.com/user-attachments/assets/3ecea60e-cb9c-40be-b9b5-fa08ad64928a)


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
```c
#include<stdio.h> 
int main()
{
    int noshel,noque; 
    scanf("%d%d",&noshel,&noque); 
    int shelarr[noshel][noshel];
    int nobookarr[noshel]; 
    int k=0,c=0;
    for(int i=0;i<noque;i++)
    {
        int queno; 
        scanf("%d",&queno);
        if(queno==1)
        {
            int shelno,nopage;
            scanf("%d%d",&shelno,&nopage);
            shelarr[shelno][k]=nopage; 
            nobookarr[shelno]=c+=1;
            k=k+1;
            
        }
        else if(queno==2)
        {
            int pshelno,pbookno;
            scanf("%d%d",&pshelno,&pbookno); 
            printf("%d",shelarr[pshelno][pbookno]);
            
        }
        else if(queno==3)
        {
            int ppshelno;
            scanf("%d",&ppshelno); 
            printf("%d",nobookarr[ppshelno]);
        }
        
    }
}
```


## Output:

![437661534-8d5ef4e7-6249-4547-962b-3c247a993e73](https://github.com/user-attachments/assets/737000a3-2bf7-4796-986d-19e1eeccd5f6)


## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:
```c
#include<stdio.h>
int main()
{
    int n; scanf("%d",&n);
    int a[n];
    int sum=0;
    for(int i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
        sum=sum+a[i];
        
    }
    printf("%d",sum);
}
```

## Output:
 ![437661711-f87c7755-9a72-4ebf-86df-fab5f93e6f55](https://github.com/user-attachments/assets/a0a09a90-dbe3-4ad9-9a1e-0b5893d37120)



## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
## EXP NO :25 C PROGRAM TO COUNT THE NUMBER OF WORDS IN A  SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```c
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    fgets(str,sizeof(str),stdin);
    int len=sizeof(str);
    int count=1;
     for(int i=0;i<len-1;i++){
         if(str[i]==' ')
         count++;
         
     }
     printf("Total number of words in the string is :%d",count);
    return 0;
}
```

## Output:

![437661803-b54e9d7f-513d-484c-a3b7-167f80d1d7db](https://github.com/user-attachments/assets/e5b10af6-0a8e-4ddf-9c16-a6a90d5c1884)



## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.

# EXP NO :26 C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:
```c
struct Node
{
    int data;
    struct Node *next;
}*head;
void display()
{
    struct Node *p; 
    p=head;
    while(p!=NULL)
    {
        printf("%d\n",p->data);
        p=p->next;
        
    }
}
```

## Output:

![437662174-4d5cf78e-2888-450d-bd9c-6374a97e77cb](https://github.com/user-attachments/assets/9e14dc48-cff2-4660-a4a5-fe136871bb5b)



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



## EXP.NO :27 C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
```c
struct Node
{
    int data;
    struct Node *next;
}*head; 
void pop()
{
    if(head==NULL)
    {
        printf("stack is empty");
        
    }
    else
    {
        head=head->next;
        
    }
}
```

## Output:

![437662429-036cb0bb-5e1d-483e-b869-94745c0e0779](https://github.com/user-attachments/assets/b2a82855-10bc-43d7-8052-09214dddff64)




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:
```c
struct Node
{
    char data;
    struct Node *next;
}*front=NULL,*rear=NULL;
void display()
{
    if(front==NULL)
    {
        printf("queue is empty");
        
    }
    else
    {
        printf("queue elements:\n");
        while(front!=NULL)
        {
            printf("%c\n",front->data);
            front=front->next;
            
        }
        
    }
}
```

## Output:
![437662542-16bac685-84d5-42b9-b865-319b7ddca7f8](https://github.com/user-attachments/assets/aeafa5a6-1291-4350-badc-2cf847408e78)


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
## EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:
```c
struct Node
{
   int data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void enqueue(int data)
{
   struct Node *p=(struct Node*)malloc(sizeof(struct Node));
   p->data=data;
   p->next=NULL;
   if(front==NULL)
   {
       front=rear=p;
       
   }
   else
   {
       rear->next=p; 
       rear=p;
       
   }
}
```

## Output:
![437663508-cc548d88-b1b3-46b8-9fe0-73a68dc7dfe8](https://github.com/user-attachments/assets/6b08f3e1-4bf3-47f7-a1ab-6602a062e9d8)



## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

### Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```c
struct Node
{
   char data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void peek()
{
    printf("%c",front->data);
}
```


## Output:

![437663967-c063cab3-74eb-4bd7-9ed1-c6c466a09bdc](https://github.com/user-attachments/assets/4153baaa-4e15-4487-8b07-c038e71afb04)



## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
