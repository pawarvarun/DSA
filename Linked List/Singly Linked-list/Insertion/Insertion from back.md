```c
#include <stdio.h>
#include <stdlib.h>

// Define a structure for the linked list node
struct node {
    int data;
    struct node *next;
};

struct node *head = NULL; // Initialize the linked list as empty

// Function to insert a new node at the back of the linked list
void insertAtBack(int data) {
    // Create a new node and allocate memory for it
    struct node *newNode = (struct node*)malloc(sizeof(struct node));

    // Assign data to the new node and set its next pointer to NULL
    newNode->data = data;
    newNode->next = NULL;

    // If the linked list is empty, make the new node the head of the list
    if (head == NULL) {
        head = newNode;
        return;
    }

    // Traverse the linked list to find the last node
    struct node *last = head;
    while (last->next != NULL) {
        last = last->next;
    }

    // Set the next pointer of the last node to the new node
    last->next = newNode;
}

int main() {
    int choice, data;

    do {
        // Prompt the user to enter data to be inserted
        printf("Enter data to be inserted: ");
        scanf("%d", &data);

        // Insert the new node at the back of the linked list
        insertAtBack(data);

        // Prompt the user to enter 1 to continue inserting or 0 to exit
        printf("Enter 1 to insert more, 0 to exit: ");
        scanf("%d", &choice);
    } while (choice != 0);

    // Display the final linked list
    printf("Final linked list: ");
    struct node *current = head;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");

    return 0;
}
```


## DryRun
---
```c
// Initialize an empty linked list
head = NULL

// First iteration:

Enter data to be inserted: 5
// A new node with data 5 is created and inserted at the back of the list
// The updated linked list is: 5 -> NULL

Enter 1 to insert more, 0 to exit: 1
// The user chooses to continue inserting

Enter data to be inserted: 8
// A new node with data 8 is created and inserted at the back of the list
// The updated linked list is: 5 -> 8 -> NULL

Enter 1 to insert more, 0 to exit: 0
// The user chooses to exit

Final linked list: 5 8
// The final linked list is displayed


// Second iteration:

Enter data to be inserted: 2
// A new node with data 2 is created and inserted at the back of the list
// The updated linked list is: 2 -> NULL

Enter 1 to insert more, 0 to exit: 1
// The user chooses to continue inserting

Enter data to be inserted: 7
// A new node with data 7 is created and inserted at the back of the list
// The updated linked list is: 2 -> 7 -> NULL

Enter 1 to insert more, 0 to exit: 0
// The user chooses to exit

Final linked list: 2 7
// The final linked list is displayed
```


front

back