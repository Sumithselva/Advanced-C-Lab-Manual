

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

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void display() {
    struct Node* p = head; 
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);  
        p = p->next;            
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    display();

    return 0;
}
```

Output:


![Screenshot 2025-05-22 144943](https://github.com/user-attachments/assets/bd019b03-926d-4272-8d8e-ec82f28819fc)



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
    } else {
        struct Node* temp = head; 
        printf("Popped element: %d\n", temp->data); 
        head = head->next; 
        free(temp); 
    }
}

void display() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* p = head;
    printf("Stack elements:\n");
    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    printf("Stack before popping:\n");
    display();

    pop();

    printf("Stack after popping:\n");
    display();

    pop();
    pop();
    pop();

    return 0;
}

```

Output:



![Screenshot 2025-05-22 145052](https://github.com/user-attachments/assets/31d79bbe-94a4-41d8-835c-db03d587b320)



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

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode; 
    } else {
        rear->next = newNode; 
        rear = newNode;       
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front; 
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d\n", temp->data); 
        temp = temp->next;          
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```

Output:


![Screenshot 2025-05-22 145147](https://github.com/user-attachments/assets/c2ad2c80-8750-427d-bd9f-43862c9697bb)


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

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    
    newNode->data = value;
    newNode->next = NULL;
    
    if (rear == NULL) {
        front = rear = newNode; 
    } else {
        rear->next = newNode;  
        rear = newNode;       
    }
    printf("%d inserted into the queue.\n", value);
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front; 
    printf("Queue elements:\n");
    while (temp != NULL) {
        printf("%d\n", temp->data); 
        temp = temp->next;         
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();

    return 0;
}
```

Output:


![Screenshot 2025-05-22 145229](https://github.com/user-attachments/assets/797edd96-295b-46f7-a2dd-5e1c5b081d0b)


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

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return -1;
    }

    return front->data;
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    int frontElement = peek();
    if (frontElement != -1) { 
        printf("Front element of the queue is: %d\n", frontElement);
    }

    return 0;
}
```

Output:



![Screenshot 2025-05-22 145318](https://github.com/user-attachments/assets/feda0293-98b5-42e7-b0f0-8c4ae7a44b4f)



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
