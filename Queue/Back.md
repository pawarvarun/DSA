```c
#include <stdio.h>

#define MAX_SIZE 10 // Maximum size of the queue

int queue[MAX_SIZE]; // Array to store the elements in the queue
int front = -1; // Index of the front element in the queue
int rear = -1; // Index of the rear element in the queue

// Function to check if the queue is empty
int is_empty() {
    if (front == -1 && rear == -1) {
        return 1;
    }
    return 0;
}

// Function to check if the queue is full
int is_full() {
    if (rear == MAX_SIZE - 1) {
        return 1;
    }
    return 0;
}

// Function to add an element to the back of the queue
void enqueue(int value) {
    if (is_full()) {
        printf("Queue is full. Cannot enqueue element.\n");
        return;
    } else if (is_empty()) {
        front = rear = 0;
    } else {
        rear++;
    }
    queue[rear] = value;
    printf("%d enqueued to the queue.\n", value);
}

// Function to remove an element from the front of the queue
void dequeue() {
    if (is_empty()) {
        printf("Queue is empty. Cannot dequeue element.\n");
        return;
    }
    printf("%d dequeued from the queue.\n", queue[front]);
    if (front == rear) {
        front = rear = -1;
    } else {
        front++;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("Queue Operations Menu\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter the value to be enqueued: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                printf("Exiting the program.\n");
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
    return 0;
}
```

back