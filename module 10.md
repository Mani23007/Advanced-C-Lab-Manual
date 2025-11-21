## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

struct Node* createNode(char value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

void search(struct Node *head, char key) {
    struct Node *temp = head;

    while (temp != NULL) {
        if (temp->data == key) {
            printf("Element '%c' found in the linked list.\n", key);
            return;
        }
        temp = temp->next;
    }

    printf("Element '%c' not found in the linked list.\n", key);
}

int main() {
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;

    // Creating linked list: A → B → C
    head = createNode('A');
    second = createNode('B');
    third = createNode('C');

    head->next = second;
    second->next = third;

    char key;
    printf("Enter character to search: ");
    scanf(" %c", &key);

    search(head, key);

    return 0;
}
```

## Output:

<img width="501" height="166" alt="image" src="https://github.com/user-attachments/assets/e0c7212b-39f3-4bf3-80a5-4fc859d2875a" />

## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
## EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
## Aim:
To write a C program to insert a node in a linked list.
## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

struct Node* insert(struct Node *head, char value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL) {
        return newNode;  // New node becomes the head
    }

    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    return head;
}

void display(struct Node *head) {
    struct Node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    char ch;

    printf("Enter characters to insert (X to stop):\n");
    while (1) {
        printf("Enter character: ");
        scanf(" %c", &ch);

        if (ch == 'X') break;

        head = insert(head, ch);
    }

    display(head);

    return 0;
}
```

## Output:

<img width="542" height="281" alt="image" src="https://github.com/user-attachments/assets/e78ac8ca-5929-4062-bee7-32c833f55cef" />


 
## Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *prev;
    struct Node *next;
};

// Function to create a new node
struct Node* createNode(char value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Insert at end for demonstration
struct Node* insertEnd(struct Node *head, char value) {
    struct Node *newNode = createNode(value);

    if (head == NULL) {
        return newNode;
    }

    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;
    return head;
}

// Traverse a doubly linked list
void traverse(struct Node *head) {
    struct Node *temp = head;

    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    char ch;

    printf("Enter characters to insert (X to stop):\n");
    while (1) {
        printf("Enter character: ");
        scanf(" %c", &ch);

        if (ch == 'X') break;

        head = insertEnd(head, ch);
    }

    traverse(head);

    return 0;
}
```

## Output:

<img width="517" height="271" alt="image" src="https://github.com/user-attachments/assets/77a77776-dd60-44f5-9e5b-03605b4e4619" />

## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *prev;
    struct Node *next;
};

struct Node* createNode(char value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

struct Node* insertEnd(struct Node *head, char value) {
    struct Node *newNode = createNode(value);

    if (head == NULL) {
        return newNode; // New node becomes head
    }

    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

void display(struct Node *head) {
    struct Node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    char ch;

    printf("Enter characters to insert (X to stop):\n");
    while (1) {
        printf("Enter character: ");
        scanf(" %c", &ch);
        if (ch == 'X') break;

        head = insertEnd(head, ch);
    }

    display(head);

    return 0;
}
```

## Output:

<img width="567" height="278" alt="image" src="https://github.com/user-attachments/assets/005f7a53-d988-45cc-866c-6e87e136a19c" />

## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
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

## Program:
```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

// Create new node
struct Node* createNode(char value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

// Insert at end (helper for building list)
struct Node* insertEnd(struct Node *head, char value) {
    struct Node *newNode = createNode(value);

    if (head == NULL) {
        return newNode;
    }

    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    return head;
}

// Delete the given element
struct Node* deleteElement(struct Node *head, char key) {
    if (head == NULL) {
        printf("List is empty.\n");
        return head;
    }

    // Case 1: deleting the first node
    if (head->data == key) {
        struct Node *temp = head;
        head = head->next;
        free(temp);
        printf("Element '%c' deleted.\n", key);
        return head;
    }

    // Case 2: deleting from middle or end
    struct Node *prev = head;
    struct Node *current = head->next;

    while (current != NULL) {
        if (current->data == key) {
            prev->next = current->next;
            free(current);
            printf("Element '%c' deleted.\n", key);
            return head;
        }
        prev = current;
        current = current->next;
    }

    // Case 3: element not found
    printf("Element '%c' not found in the list.\n", key);
    return head;
}

// Display list
void display(struct Node *head) {
    struct Node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    char ch, key;

    printf("Enter characters to insert (X to stop):\n");
    while (1) {
        printf("Enter character: ");
        scanf(" %c", &ch);
        if (ch == 'X') break;
        head = insertEnd(head, ch);
    }

    display(head);

    printf("Enter character to delete: ");
    scanf(" %c", &key);

    head = deleteElement(head, key);

    display(head);

    return 0;
}
```


## Output:

<img width="507" height="357" alt="image" src="https://github.com/user-attachments/assets/292fcef3-4d21-4d01-913f-9bf9d207b961" />


## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





