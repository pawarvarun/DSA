```c
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a singly linked list node
struct Node {
    int data;
    struct Node* next;
};

// Function to delete a node from a singly linked list given the previous node
void deleteNode(struct Node* prevNode) {
    // If the previous node or the node to be deleted is NULL, return
    if (prevNode == NULL || prevNode->next == NULL) {
        printf("Invalid node.");
        return;
    }
    
    // Store the node to be deleted and the next node
    struct Node* currentNode = prevNode->next;
    struct Node* nextNode = currentNode->next;
    
    // Update the previous node's next pointer to skip over the node to be deleted
    prevNode->next = nextNode;
    
    // Free the memory of the node to be deleted
    free(currentNode);
}

int main() {
    // Initialize the head pointer to NULL
    struct Node* head = NULL;
    
    // Insert some nodes into the list (not shown here)
    
    // Find the node to be deleted (not shown here)
    struct Node* prevNode = /* pointer to the previous node */;
    
    // Delete the node from the list
    deleteNode(prevNode);
    
    return 0;
}
```


mid