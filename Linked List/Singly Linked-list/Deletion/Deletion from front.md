```c
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a singly linked list node
struct Node {
    int data;
    struct Node* next;
};

// Function to delete the first node from a singly linked list
void deleteFirstNode(struct Node** head) {
    // If the list is empty, return
    if (*head == NULL) {
        printf("List is empty.");
        return;
    }
    
    // Store the current head node and the next node
    struct Node* current = *head;
    struct Node* nextNode = current->next;
    
    // Update the head pointer to point to the next node
    *head = nextNode;
    
    // Free the memory of the current head node
    free(current);
}

int main() {
    // Initialize the head pointer to NULL
    struct Node* head = NULL;
    
    // Insert some nodes into the list (not shown here)
    
    // Delete the first node from the list
    deleteFirstNode(&head);
    
    return 0;
}
```



front