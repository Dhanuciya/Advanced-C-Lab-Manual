EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node{
    int data;
    struct node *next;
};

void search(struct node *head, int key){
    int pos = 1;
    struct node *temp = head;

    while(temp != NULL){
        if(temp->data == key){
            printf("Element found at position %d\n", pos);
            return;
        }
        temp = temp->next;
        pos++;
    }

    printf("Element not found in the linked list\n");
}

int main(){
    struct node *head = NULL, *temp, *newnode;
    int n, i, value, key;
    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        newnode = (struct node *)malloc(sizeof(struct node));
        printf("Enter data: ");
        scanf("%d", &value);
        newnode->data = value;
        newnode->next = NULL;

        if(head == NULL){
            head = newnode;
            temp = newnode;
        }
        else{
            temp->next = newnode;
            temp = newnode;
        }
    }

    printf("Enter element to search: ");
    scanf("%d", &key);
    search(head, key);
    return 0;
}
~~~
Output:

<img width="502" height="400" alt="image" src="https://github.com/user-attachments/assets/20ff881c-2634-4017-a100-3952658c00aa" />


Result:
Thus, the program to search a given element in the given linked list is verified successfully.


EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.

Aim:
To write a C program to insert a node in a linked list.

Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node
{
    char data;
    struct node *next;
}*head;

void insert(char value){
    struct node *newnode, *temp;
    newnode = (struct node *)malloc(sizeof(struct node));
    newnode->data = value;
    newnode->next = NULL;

    if(head == NULL){
        head = newnode;
    }
    else{
        temp = head;

        while(temp->next != NULL){
            temp = temp->next;
        }
        temp->next = newnode;
    }
}

void display(){
    struct node *temp = head;
    printf("Linked List: ");

    while(temp != NULL){
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main(){
    int n, i;
    char value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        printf("Enter character: ");
        scanf(" %c", &value);

        insert(value);
    }

    display();
    return 0;
}
~~~

Output:

<img width="484" height="361" alt="image" src="https://github.com/user-attachments/assets/910d3f7d-0daa-40de-9e1a-9c3207d30aa9" />


Result:
Thus, the program to insert a node in a linked list is verified successfully.


EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};

int main(){
    struct node *head = NULL, *temp = NULL, *newnode;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        newnode = (struct node *)malloc(sizeof(struct node));

        printf("Enter data: ");
        scanf("%d", &value);

        newnode->data = value;
        newnode->prev = NULL;
        newnode->next = NULL;

        if(head == NULL){
            head = newnode;
            temp = newnode;
        }
        else{
            temp->next = newnode;
            newnode->prev = temp;
            temp = newnode;
        }
    }

    printf("\nDoubly Linked List Elements:\n");
    temp = head;

    while(temp != NULL){
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
    return 0;
}
~~~

Output:

<img width="439" height="412" alt="image" src="https://github.com/user-attachments/assets/37ae1422-7094-431a-bee7-4d1164524d50" />


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 


EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};
struct node *head = NULL;

void insert(int value){
    struct node *newNode, *temp;

    newNode = (struct node *)malloc(sizeof(struct node));

    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;

    if(head == NULL){
        head = newNode;
    }
    else{
        temp = head;
        while(temp->next != NULL){
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display(){
    struct node *temp = head;
    printf("Doubly Linked List: ");

    while(temp != NULL){
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main(){
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        printf("Enter data: ");
        scanf("%d", &value);
        insert(value);
    }

    display();
    return 0;
}
~~~

Output:

<img width="447" height="348" alt="image" src="https://github.com/user-attachments/assets/42a45fb5-05dc-44ae-9136-02700f4bbfad" />


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.


EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.

Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

struct node *head = NULL;

void insert(int value){
    struct node *newnode, *temp;
    newnode = (struct node *)malloc(sizeof(struct node));
    newnode->data = value;
    newnode->next = NULL;

    if(head == NULL){
        head = newnode;
    }
    else{
        temp = head;
        while(temp->next != NULL){
            temp = temp->next;
        }
        temp->next = newnode;
    }
}

void deleteElement(int key){
    struct node *temp = head, *prev = NULL;

    if(head == NULL){
        printf("Linked List is Empty\n");
        return;
    }

    if(temp != NULL && temp->data == key){
        head = temp->next;
        free(temp);
        printf("Element %d deleted successfully\n", key);
        return;
    }

    while(temp != NULL && temp->data != key){
        prev = temp;
        temp = temp->next;
    }

    if(temp == NULL){
        printf("Element not found in the list\n");
        return;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted successfully\n", key);
}

void display(){
    struct node *temp = head;
    printf("Linked List: ");

    while(temp != NULL){
        printf("%d -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main(){
    int n, i, value, key;
    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for(i = 0; i < n; i++){
        printf("Enter data: ");
        scanf("%d", &value);
        insert(value);
    }

    printf("\nBefore Deletion:\n");
    display();
    printf("Enter element to delete: ");
    scanf("%d", &key);
    deleteElement(key);
    printf("\nAfter Deletion:\n");
    display();

    return 0;
}
~~~

Output:

<img width="462" height="572" alt="image" src="https://github.com/user-attachments/assets/e83bcb30-302a-4de5-a021-d47f67268b4f" />


Result:
Thus, the function that deletes a given element from a linked list is verified successfully.


