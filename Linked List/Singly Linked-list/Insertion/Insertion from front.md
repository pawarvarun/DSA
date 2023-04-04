```c
#include<stdio.h>  
#include<stdlib.h>  
void beginsert(int);  
struct node  
{  
    int data;  
    struct node *next;  
};  
struct node *head;  
void main ()  
{  
    int choice,item;  
    do   
    {  
        printf("\nEnter the item which you want to insert?\n");  
        scanf("%d",&item);  
        beginsert(item);  
        printf("\nPress 0 to insert more ?\n");  
        scanf("%d",&choice);  
    }while(choice == 0);  
}  
void beginsert(int item)  
    {  
        struct node *ptr = (struct node *)malloc(sizeof(struct node *));  
        if(ptr == NULL)  
        {  
            printf("\nOVERFLOW\n");  
        }  
        else  
        {  
            ptr->data = item;  
            ptr->next = head;  
            head = ptr;  
            printf("\nNode inserted\n");  
        }  
          
    }
```


## DryRun
---
```css
Enter the item which you want to insert?
10

Press 0 to insert more ?
1

Enter the item which you want to insert?
20

Press 0 to insert more ?
1

Enter the item which you want to insert?
30

Press 0 to insert more ?
1

Enter the item which you want to insert?
40

Press 0 to insert more ?
0
```

Here, the user wants to insert the values `10`, `20`, `30`, and `40` into the linked list.

The program will execute as follows:

1.  The `main()` function is called for the first time, which prompts the user to enter the first item to be inserted and calls the `beginsert()` function with the item value.
    
2.  The `beginsert()` function is called with `item` value `10`. A new node is created using the `malloc()` function to allocate memory for the node structure. The `data` member of the new node is set to `10`, and the `next` pointer of the new node is set to the current value of the `head` pointer, which is `NULL`.
    
3.  The `head` pointer is updated to point to the new node.
    
4.  The program prints the message "Node inserted".
    
5.  The `main()` function prompts the user whether to insert more items. Since the user enters `1`, the program executes the do-while loop again.
    
6.  The `main()` function is called for the second time, which prompts the user to enter the second item to be inserted and calls the `beginsert()` function with the item value.
    
7.  The `beginsert()` function is called with `item` value `20`. A new node is created using the `malloc()` function to allocate memory for the node structure. The `data` member of the new node is set to `20`, and the `next` pointer of the new node is set to the current value of the `head` pointer, which points to the first node with value `10`.
    
8.  The `head` pointer is updated to point to the new node.
    
9.  The program prints the message "Node inserted".
    
10.  The `main()` function prompts the user whether to insert more items. Since the user enters `1`, the program executes the do-while loop again.
    
11.  The `main()` function is called for the third time, which prompts the user to enter the third item to be inserted and calls the `beginsert()` function with the item value.
    
12.  The `beginsert()` function is called with `item` value `30`. A new node is created using the `malloc()` function to allocate memory for the node structure. The `data` member of the new node is set to `30`, and the `next` pointer of the new node is set to the current value of the `head` pointer, which points to the second node with value `20`.
    
13.  The `head` pointer is updated to point to the new node.
    
14.  The program prints the message "Node inserted".
    
15.  The `main()` function prompts the user whether to insert more items. Since the user enters `1`, the program executes the do-while loop again.
    
16.  The `main()` function is called for the fourth time, which prompts the user to enter the fourth item to be inserted and calls the `beginsert()` function with the item value.
    
17.  The `beginsert()` function is called with `item` value `40`. A new node is created using the `malloc()` function to allocate memory for



front