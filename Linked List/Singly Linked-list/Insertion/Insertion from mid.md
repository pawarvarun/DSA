```c
#include<stdio.h>
#include<stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void insert_at_mid(int data, int position, struct Node **head) {
    struct Node *new_node = (struct Node*) malloc(sizeof(struct Node));
    new_node->data = data;
    new_node->next = NULL;

    if(*head == NULL && position != 1) {
        printf("Invalid position, list is empty!\n");
        return;
    }

    if(*head == NULL && position == 1) {
        *head = new_node;
        printf("Node inserted at position %d.\n", position);
        return;
    }

    if(position == 1) {
        new_node->next = *head;
        *head = new_node;
        printf("Node inserted at position %d.\n", position);
        return;
    }

    struct Node *current_node = *head;
    int count = 1;
    while(count < position-1 && current_node != NULL) {
        current_node = current_node->next;
        count++;
    }

    if(current_node == NULL) {
        printf("Invalid position, list size is smaller than the position.\n");
        return;
    }

    new_node->next = current_node->next;
    current_node->next = new_node;
    printf("Node inserted at position %d.\n", position);
    return;
}

void print_list(struct Node *node) {
    while(node != NULL) {
        printf("%d ", node->data);
        node = node->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    insert_at_mid(5, 1, &head);  // Insert at position 1 (empty list)
    print_list(head);
    insert_at_mid(7, 2, &head);  // Insert at position 2
    print_list(head);
    insert_at_mid(9, 1, &head);  // Insert at position 1 (non-empty list)
    print_list(head);
    insert_at_mid(3, 4, &head);  // Invalid position
    print_list(head);
    insert_at_mid(8, 3, &head);  // Insert at position 3
    print_list(head);
    int num,post;
    scanf("%d %d", &num, &post);
    insert_at_mid(num,post,&head)
    return 0;
}
```


## DryRun
---
1.  `head` is initialized to `NULL`.
2.  `insert_at_mid(5, 1, &head)` is called.
    -   A new node is created with `data=5` and `next=NULL`.
    -   Since the list is empty and the position is 1, the new node becomes the head of the list.
    -   The function displays "Node inserted at position 1." and returns.
    -   The linked list is printed: `5`
3.  `insert_at_mid(7, 2, &head)` is called.
    -   A new node is created with `data=7` and `next=NULL`.
    -   The new node is inserted at position 2, after the head node.
    -   The function displays "Node inserted at position 2." and returns.
    -   The linked list is printed: `5 7`
4.  `insert_at_mid(9, 1, &head)` is called.
    -   A new node is created with `data=9` and `next=NULL`.
    -   The new node becomes the new head of the list.
    -   The function displays "Node inserted at position 1." and returns.
    -   The linked list is printed: `9 5 7`
5.  `insert_at_mid(3, 4, &head)` is called.
    -   The position is invalid because the list size is smaller than the position.
    -   The function displays "Invalid position, list size is smaller than the position." and returns.
    -   The linked list is printed: `9 5 7`
6.  `insert_at_mid(8, 3, &head)` is called.
    -   A new node is created with `data=8` and `next=NULL`.
    -   The new node is inserted at position 3, after the node with `data=5`.
    -   The function displays "Node inserted at position 3." and returns.
    -   The linked list is printed: `9 5 8 7`


mid
