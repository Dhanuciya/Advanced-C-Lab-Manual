EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.

Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};
struct Node *head = NULL;

void push(int value){
    struct Node *newNode;
    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void display(){
    struct Node *p;

    if(head == NULL){
        printf("Stack is Empty\n");
        return;
    }

    printf("Stack Elements:\n");
    p = head;

    while(p != NULL){
        printf("%d\n", p->data);
        p = p->next;
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

<img width="467" height="587" alt="image" src="https://github.com/user-attachments/assets/32d6ba71-4314-495e-a278-fe26c8f47990" />


Result:
Thus, the program to display stack elements using linked list is verified successfully. 


EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.

Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};
struct Node *head = NULL;

void push(int value){
    struct Node *newNode;
    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop(){
    struct Node *temp;

    if(head == NULL){
        printf("Stack is Empty\n");
        return;
    }

    temp = head;
    printf("Popped Element: %d\n", head->data);
    head = head->next;
    free(temp);
}

void display(){
    struct Node *p = head;

    if(head == NULL){
        printf("Stack is Empty\n");
        return;
    }

    printf("Stack Elements:\n");
    while(p != NULL){
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main(){
    push(10);
    push(20);
    push(30);
    push(40);

    printf("Before Pop Operation:\n");
    display();
    pop();
    printf("\nAfter Pop Operation:\n");
    display();

    return 0;
}
~~~

Output:

<img width="452" height="584" alt="image" src="https://github.com/user-attachments/assets/727c284f-800a-4165-a3ee-2dfb9712cb3c" />


Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.

Aim:
To write a C program to display queue elements using linked list.

Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value){
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if(front == NULL){
        front = rear = newNode;
    }
    else{
        rear->next = newNode;
        rear = newNode;
    }
}

void display(){
    struct Node *temp;

    if(front == NULL){
        printf("Queue is Empty\n");
        return;
    }

    temp = front;
    printf("Queue Elements:\n");
    while(temp != NULL){
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main(){
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}
~~~

Output:

<img width="482" height="262" alt="image" src="https://github.com/user-attachments/assets/6c7ac387-4a0a-4d68-894c-02e47250339e" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.

 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value){
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if(front == NULL){
        front = rear = p;
    }
    else{
        rear->next = p;
        rear = p;
    }

    printf("Element %d inserted into the queue.\n", value);
}

void display(){
    struct Node *temp = front;

    if(front == NULL){
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue Elements: ");

    while(temp != NULL){
        printf("%d ", temp->data);
        temp = temp->next;
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

<img width="463" height="274" alt="image" src="https://github.com/user-attachments/assets/33303f89-e0c2-4eeb-8c1e-45a3a5b0d64b" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.


EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

Aim:
The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:
1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value){
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if(front == NULL){
        front = rear = newNode;
    }
    else{
        rear->next = newNode;
        rear = newNode;
    }
}

int peek(){
    if(front == NULL){
        printf("Queue is Empty\n");
        return -1;
    }
    return front->data;
}

int main(){
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    printf("Front Element (Peek): %d\n", peek());
    return 0;
}
~~~

Output:

<img width="510" height="233" alt="image" src="https://github.com/user-attachments/assets/d14d4182-de31-4034-a935-f0ed000bd83e" />


Result:
Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
