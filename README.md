#include <stdio.h>

#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;


void enqueue(int temp) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert %d\n", temp);
        return;
    }

    if (front == -1)
        front = 0;

    rear++;
    queue[rear] = temp;
    printf("Enqueued Temperature: %d\n", temp);
}


void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow! No data to remove\n");
        return;
    }

    printf("Dequeued Temperature: %d\n", queue[front]);
    front++;
}


void display() {
    if (front == -1 || front > rear) {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Contents: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main() {
    enqueue(30);
    enqueue(31);
    enqueue(29);
    enqueue(32);
    enqueue(28);

    enqueue(35);  

    display();

    dequeue();
    dequeue();
    dequeue();
    dequeue();
    dequeue();

    dequeue();     

    return 0;
}
