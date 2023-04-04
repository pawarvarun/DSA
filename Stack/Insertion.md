```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

int stack[MAX_SIZE];
int top = -1;

void push(int value) {
    if (top == MAX_SIZE - 1) {
        printf("Stack overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("Pushed %d onto the stack\n", value);
    }
}

void pop() {
    if (top == -1) {
        printf("Stack underflow\n");
    } else {
        printf("Popped %d from the stack\n", stack[top]);
        top--;
    }
}

int peek(int index) {
    if (top == -1) {
        printf("Stack is empty\n");
        return -1;
    } else if (index < 0 || index > top) {
        printf("Invalid index\n");
        return -1;
    } else {
        printf("Element at index %d is %d\n", index, stack[top - index]);
        return stack[top - index];
    }
}

void change(int index, int value) {
    if (top == -1) {
        printf("Stack is empty\n");
    } else if (index < 0 || index > top) {
        printf("Invalid index\n");
    } else {
        stack[top - index] = value;
        printf("Changed element %d to %d\n", index, value);
    }
}

void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Elements in the stack are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    int choice, value, index;
    do {
        printf("\nStack Operations Menu\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Peek\n");
        printf("4. Change\n");
        printf("5. Display\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter the value to be pushed: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                printf("Enter the index of the element to peek: ");
                scanf("%d", &index);
                peek(index);
                break;
            case 4:
                printf("Enter the index of the element to change: ");
                scanf("%d", &index);
                printf("Enter the new value: ");
                scanf("%d", &value);
                change(index, value);
                break;
            case 5:
                display();
                break;
            case 6:
                printf("Exiting the program\n");
                exit(0);
                break;
            default:
                printf("Invalid choice\n");
        }
    } while (choice != 6);

    return 0;
}
```




Insertion

Deletion

Check

display