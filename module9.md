EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.

Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
~~~
#include <stdio.h>

#define MAX 10

int stack[MAX];
int top = -1;

void push(int data)
{
    if(top == MAX - 1){
        printf("Stack Overflow\n");
        return;
    }
    top++;
    stack[top] = data;
}

void display(){
    int i;
    if(top == -1){
        printf("Stack is Empty\n");
        return;
    }
    printf("Stack Elements are:\n");
    for(i = top; i >= 0; i--){
        printf("%d\n", stack[i]);
    }
}

int main(){
    int n, i, value;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }
    display();
    return 0;
}
~~~

Output:

<img width="443" height="426" alt="image" src="https://github.com/user-attachments/assets/8bb15c47-6bc0-4557-9235-adb66a2fcf62" />


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.

Aim:
To create a C program to push the given element in to a stack using array.

Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
~~~
#include <stdio.h>
#define MAX 10

int stack[MAX];
int top = -1;

void push(int data){
    if(top == MAX - 1){
        printf("Stack Overflow\n");
        return;
    }

    top++;
    stack[top] = data;
    printf("Element %d pushed into stack.\n", data);
}

void display(){
    int i;
    if(top == -1){
        printf("Stack is Empty\n");
        return;
    }

    printf("Stack Elements:\n");
    for(i = top; i >= 0; i--){
        printf("%d\n", stack[i]);
    }
}

int main(){
    int value;
    printf("Enter the element to push: ");
    scanf("%d", &value);
    push(value);
    display();
    return 0;
}
~~~

Output:

<img width="450" height="307" alt="image" src="https://github.com/user-attachments/assets/0f8337cb-c880-426c-95b5-a564974b25f9" />


Result:
Thus, the program to push the given element in to a stack using array is verified successfully


EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
~~~
#include <stdio.h>
#define MAX 10

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int data){
    if(rear == MAX - 1){
        printf("Queue Overflow\n");
        return;
    }
    if(front == -1)
        front = 0;
    rear++;
    queue[rear] = data;
}

void display(){
    int i;

    if(front == -1 || front > rear){
        printf("Queue is Empty\n");
        return;
    }
    printf("Queue Elements are:\n");

    for(i = front; i <= rear; i++){
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main(){
    int n, i, value;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }
    display();
    return 0;
}
~~~

Output:

<img width="413" height="346" alt="image" src="https://github.com/user-attachments/assets/27c6a221-bf0a-4105-93c6-4ecdbea0c132" />


Result:
Thus, the program to display queue elements using array is verified successfully.

 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
~~~
#include <stdio.h>
#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int data){
    if(rear == SIZE - 1){
        printf("Queue Overflow\n");
        return;
    }

    if(front == -1)
        front = 0;
    rear++;
    queue[rear] = data;
    printf("Element %d inserted into the queue.\n", data);
}

void display(){
    int i;

    if(front == -1){
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Elements are:\n");
    for(i = front; i <= rear; i++){
        printf("%d ", queue[i]);
    }

    printf("\n");
}

int main(){
    int value;

    printf("Enter an element to insert: ");
    scanf("%d", &value);

    enqueue(value);

    display();

    return 0;
}
~~~

Output:

<img width="477" height="319" alt="image" src="https://github.com/user-attachments/assets/9822849a-af30-4153-80c5-609cec1c3581" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.

 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

Aim:
To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.

Program:
~~~
#include <stdio.h>
#define SIZE 10

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int data){
    if(rear == SIZE - 1){
        printf("Queue Overflow\n");
        return;
    }

    if(front == -1)
        front = 0;
    queue[++rear] = data;
}

void dequeue(){
    int item;
    if(front == -1){
        printf("Queue Underflow\n");
        return;
    }

    item = queue[front];
    printf("Deleted Element: %d\n", item);
    front++;

    if(front > rear){
        front = -1;
        rear = -1;
    }
}

void display(){
    int i;

    if(front == -1){
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Elements: ");
    for(i = front; i <= rear; i++){
        printf("%d ", queue[i]);
    }

    printf("\n");
}

int main(){
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    printf("Before Deletion:\n");
    display();

    dequeue();

    printf("After Deletion:\n");
    display();

    return 0;
}
~~~

Output:

<img width="478" height="347" alt="image" src="https://github.com/user-attachments/assets/f7baa643-0e9f-4cc9-a7b3-847a7bc30abc" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
