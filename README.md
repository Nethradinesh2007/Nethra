1)Selection sort without using dynamic memory allocation 
Program: 
#include <stdio.h> 
void selectionSort(int arr[], int n) { int i, j, minIndex, temp;
 for (i = 0; i < n - 1; i++) { minIndex = i;
 for (j = i + 1; j < n; j++)
 { if (arr[j] < arr[minIndex]) { minIndex = j; } }
 if (minIndex != i) 
{ temp = arr[i];
 arr[i] = arr[minIndex]; arr[minIndex] = temp; } } } 
int main() { 
int arr[] = {64, 25, 12, 22, 11}; int n = sizeof(arr) / sizeof(arr[0]);
 selectionSort(arr, n); printf("Sorted array:\n"); 
for (int i = 0; i < n; i++)
 { printf("%d ", arr[i]); } 
return 0; } 


2)Selection sort with using dynamic memory allocation 

Program: 
#include <stdio.h> 
#include <stdlib.h>
 void selectionSort(int *arr, int n) { int i, j, minIndex, temp; 
for (i = 0; i < n - 1; i++) { minIndex = i; 
for (j = i + 1; j < n; j++) 
{ if (arr[j] < arr[minIndex]) { minIndex = j;
 } } 
if (minIndex != i) 
{ temp = arr[i];
 arr[i] = arr[minIndex]; arr[minIndex] = temp; 
} } } 
int main() 
{ int n;
 int *arr; 
printf("Enter number of elements: "); 
scanf("%d", Cn); 
arr = (int *)malloc(n * sizeof(int)); 
if (arr == NULL) 
{ printf("Memory allocation failed\n");
 return 1; }
 printf("Enter %d elements:\n", n); for (int i = 0; i < n; i++) { scanf("%d", Carr[i]); 
} selectionSort(arr, n); printf("Sorted array:\n"); 
for (int i = 0; i < n; i++) { printf("%d ", arr[i]); } free(arr); 
return 0; } 


3)Initialization of malloc() function into 0 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
#include <string.h> 
int main() 
{ int n = 5; 
int *arr = (int *)malloc(n * sizeof(int)); 
if (arr == NULL) 
{ printf("Memory allocation failed\n"); 
return 1; } 
memset(arr, 0, n * sizeof(int));
 for (int i = 0; i < n; i++) { printf("%d ", arr[i]); } free(arr); 
return 0; } 


4)Declaration of two dimensional array using dynamic memory allocation 

Program:
 #include <stdio.h>
 #include <stdlib.h> 
int main() 
{ int rows = 3, cols = 4; 
int **arr;
 arr = (int **)malloc(rows * sizeof(int *)); 
for (int i = 0; i < rows; i++) { arr[i] = (int *)malloc(cols * sizeof(int));
 } for (int i = 0; i < rows; i++) { for (int j = 0; j < cols; j++) { arr[i][j] = i + j;
 printf("%d ", arr[i][j]); } printf("\n"); }
 for (int i = 0; i < rows; i++) { free(arr[i]); } 
free(arr);
 return 0; } 

5)Pattern matching

 Program: 
#include <stdio.h> 
#include <string.h> 
void patternMatch(char text[], char pattern[]) 
{ int n = strlen(text); 
int m = strlen(pattern); 
for (int i = 0; i <= n - m; i++) { int j; 
for (j = 0; j < m; j++) 
{ if (text[i + j] != pattern[j]) break; } 
if (j == m) 
{ printf("Pattern found at index %d\n", i); } } } 
int main() 
{ char text[] = "ABABDABACDABABCABAB";
 char pattern[] = "ABABCABAB"; patternMatch(text, pattern);
 return 0;} 

6)Self referential structure

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node *next; 
};
 int main() 
{ struct Node *head, *second, *third; 
head = (struct Node *)malloc(sizeof(struct Node)); second = (struct Node *)malloc(sizeof(struct Node));
 third = (struct Node *)malloc(sizeof(struct Node)); head->data = 10; 
head->next = second;
second->data = 20; 
second->next = third; 
third->data = 30; 
third>next = NULL; 
struct Node *temp = head; printf("Linked List elements:\n"); while (temp != NULL) 
{ printf("%d -> ", temp->data); 
temp = temp->next; } 
printf("NULL\n"); 
free(head); 
free(second); 
free(third); 
return 0; } 

7)Pre increment and Post increment

 Program: 
#include <stdio.h>
 int main() 
{ int i = 5; 
printf("Pre-increment: %d\n", ++i); printf("Post-increment: %d\n", i++); printf("Final value of i: %d\n", i); return 0; } 

8)Pre decrement and Post decrement:

 Program: 
#include <stdio.h> 
int main() 
{ int i = 5; 
printf("Pre-decrement: %d\n", --i); printf("Post-decrement: %d\n", i--); printf("Final value of i: %d\n", i); return 0; } 

9)Regular Ǫueue

 Program: 
#include <stdio.h> 
#define SIZE 
int queue[SIZE];
 int front = -1, rear = -1;
 void enqueue(int value)
 { if (rear == SIZE - 1) { printf("Queue Overflow\n"); return; 
} if (front == -1)
 front = 0; 
rear++; 
queue[rear] = value; 
printf("%d inserted\n", value); } void dequeue() 
{ if (front == -1 || front > rear) { printf("Queue Underflow\n"); return; 
} 
printf("%d deleted\n", queue[front]); 
front++; 
if (front > rear) { 
front = rear = -1; // reset queue } } 
void display() 
{ if (front == -1) 
{ printf("Queue is empty\n"); return; 
} printf("Queue elements: ");
 for (int i = front; i <= rear; i++) { printf("%d ", queue[i]); } printf("\n"); } 
int main() 
{ int choice, value; 
do { printf("\n1.Enqueue\n2.Dequeue\n3.Display\n4.Exit\n"); 
printf("Enter choice: "); scanf("%d", Cchoice);
 switch (choice)
 { case 1: printf("Enter value: "); scanf("%d", Cvalue); 
enqueue(value); 
break; 
case 2: dequeue();
 break; 
case 3: display();
 break; 
case 4: printf("Exiting...\n"); break; 
default: printf("Invalid choice\n");
 } } 
while (choice != 4); 
return 0; } 

10)Operations of linked list

Program: 
#include <stdio.h>
#include <stdlib.h> 
struct Node 
{ int data; 
struct Node *next;
 }; 
struct Node* head = NULL;
 struct Node* createNode(int value) { struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->data = value; 
newNode->next = NULL;
 return newNode;
} 
void insertAtBeginning(int value) { struct Node* newNode = createNode(value); 
newNode->next = head; 
head = newNode; 
printf("%d inserted at beginning.\n", value); }
 void insertAtEnd(int value) { struct Node* newNode = createNode(value);
 if(head == NULL) { head = newNode; } 
else { struct Node* temp = head; while(temp->next != NULL) 
temp = temp->next; 
temp->next = newNode; } 
printf("%d inserted at end.\n", value); }
 void deleteFromBeginning() { if(head == NULL)
 { printf("List is empty.\n"); return; } 
struct Node* temp = head; 
head = head->next; 
printf("%d deleted from beginning.\n", temp->data); 
free(temp); 
}
 void deleteFromEnd()
 { if(head == NULL) 
{ printf("List is empty.\n"); return; } 
if(head->next == NULL) 
{ printf("%d deleted from end.\n", head->data); 
free(head); 
head = NULL; 
return; } 
struct Node* temp = head; while(temp->next->next != NULL)
 temp = temp->next;
 printf("%d deleted from end.\n", temp->next->data); 
free(temp->next);
 temp->next = NULL;
 } void displayList() 
{ if(head == NULL)
 { printf("List is empty.\n"); return; 
} struct Node* temp = head; printf("Linked List: "); 
while(temp != NULL) 
{ printf("%d -> ", temp->data); 
temp = temp->next; } printf("NULL\n"); }
 int main() 
{ int choice, value;
 do { 
printf("\n--- Linked List Operations ---\n");
 printf("1. Insert at Beginning\n2. Insert at End\n3. Delete from Beginning\n");
 printf("4. Delete from End\n5. Display\n6. Exit\n");
 printf("Enter choice: "); scanf("%d", Cchoice); 
switch(choice) 
{ case 1: printf("Enter value to insert: "); 
scanf("%d", Cvalue); insertAtBeginning(value);
 break; 
case 2: printf("Enter value to insert: ");
 scanf("%d", Cvalue); insertAtEnd(value);
 break; 
case 3: deleteFromBeginning(); 
break; 
case 4: deleteFromEnd(); 
break; 
case 5: displayList(); 
break; 
case 6: printf("Exiting program.\n"); 
break; 
default: printf("Invalid choice.\n"); } } 
while(choice != 6); 
return 0; } 

11)Linked list using Stacks 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node 
{ int data; 
struct Node* next; }; 
struct Node* top = NULL; 
void push(int value) 
{ struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); if(newNode == NULL) { 
printf("Stack overflow\n");
 return; 
} newNode->data = value; newNode->next = top; 
top = newNode; 
printf("%d pushed onto stack\n", value); } 
void pop() 
{ if(top == NULL) { printf("Stack underflow\n");
 return; } 
struct Node* temp = top; 
printf("%d popped from stack\n", temp->data); 
top = top->next; 
free(temp); } 
void display()
 { if(top == NULL) { printf("Stack is empty\n"); 
return; } 
struct Node* temp = top; printf("Stack elements (top to bottom): ");
 while(temp != NULL) 
{ printf("%d ", temp->data); 
temp = temp->next;
 } printf("\n"); 
} int main()
 { int choice, value; 
do { 
printf("\n--- Stack Operations ---\n"); 
printf("1. Push\n2. Pop\n3. Display\n4. Exit\n"); 
printf("Enter choice: "); scanf("%d", Cchoice); 
switch(choice)
 { case 1: 
printf("Enter value to push: "); scanf("%d", Cvalue); 
push(value); 
break; 
case 2: pop(); 
break; 
case 3: display(); 
break; 
case 4: printf("Exiting...\n"); break; 
default: printf("Invalid choice\n"); } }
 while(choice != 4); 
return 0; } 

12)

