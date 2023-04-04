```c
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a singly linked list node
struct Node {
    int data;
    struct Node* next;
};

// Function to delete the last node of a singly linked list
void deleteLastNode(struct Node** head) {
    // If the list is empty, return
    if (*head == NULL) {
        printf("List is empty.");
        return;
    }
    
    // If the list has only one node, delete it and set the head to NULL
    if ((*head)->next == NULL) {
        free(*head);
        *head = NULL;
        return;
    }
    
    // Traverse the list to find the last node and the second-to-last node
    struct Node* currentNode = *head;
    struct Node* secondLastNode = NULL;
    while (currentNode->next != NULL) {
        secondLastNode = currentNode;
        currentNode = currentNode->next;
    }
    
    // Set the second-to-last node's next pointer to NULL and free the memory of the last node
    secondLastNode->next = NULL;
    free(currentNode);
}

int main() {
    // Initialize the head pointer to NULL
    struct Node* head = NULL;
    
    // Insert some nodes into the list (not shown here)
    
    // Delete the last node from the list
    deleteLastNode(&head);
    
    return 0;
}
```

back