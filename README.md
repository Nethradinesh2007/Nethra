1)Selection sort without using dynamic memory allocation
 
Program: 
#include <stdio.h> 
void selectionSort(int arr[], int n)
{ int i, j, minIndex, temp;
for (i = 0; i < n - 1; i++)
 { minIndex = i;
 for (j = i + 1; j < n; j++)
{ if (arr[j] < arr[minIndex])
{ minIndex = j; } }
if (minIndex != i)
{ temp = arr[i];
arr[i] = arr[minIndex];
arr[minIndex] = temp; } } }
int main() { 
int arr[] = {64, 25, 12, 22, 11};
int n = sizeof(arr) / sizeof(arr[0]);
selectionSort(arr, n);
printf("Sorted array:\n");
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

12)Linked list using Ǫueues 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node 
{ int data; 
struct Node* next; }; 
struct Node* front = NULL; 
struct Node* rear = NULL; 
void enqueue(int value) 
{ struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); if(newNode == NULL) 
{ printf("Memory allocation failed\n"); 
return; } 
newNode->data = value; 
newNode->next = NULL; 
if(rear == NULL)
{ // Queue is empty 
front = rear = newNode; } 
else 
{ rear->next = newNode;
 rear = newNode; }
 printf("%d enqueued\n", value);} 
void dequeue() 
{ if(front == NULL) 
{ printf("Queue underflow\n"); return; 
} struct Node* temp = front; printf("%d dequeued\n", temp->data); front = front->next; 
if(front == NULL) 
{ // Queue becomes empty 
rear = NULL; } 
free(temp); } 
void display() 
{ if(front == NULL) 
{ printf("Queue is empty\n"); return; } 
struct Node* temp = front; printf("Queue elements (front to rear): ");
 while(temp != NULL) 
{ printf("%d ", temp->data);
 temp = temp->next; } printf("\n"); } 
int main() 
{ int choice, value; 
do { printf("\n--- Queue Operations ---\n"); 
printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n"); 
printf("Enter choice: "); scanf("%d", Cchoice); 
switch(choice) { case 1: printf("Enter value to enqueue: "); scanf("%d", Cvalue); 
enqueue(value); 
break; 
case 2: dequeue(); 
break; 
case 3: display(); 
break; 
case 4: printf("Exiting...\n"); break; 
default: printf("Invalid choice\n"); } } 
while(choice != 4);
return 0; } 

13) Sparse Matrix 

Program: 
#include <stdio.h> 
int main() 
{ int rows, cols, nonZero; printf("Enter number of rows and columns: "); 
scanf("%d %d", Crows, Ccols); 
int matrix[rows][cols]; printf("Enter elements of the matrix:\n"); 
for(int i = 0; i < rows; i++) { for(int j = 0; j < cols; j++) { scanf("%d", Cmatrix[i][j]); } } nonZero = 0; 
for(int i = 0; i < rows; i++) for(int j = 0; j < cols; j++) if(matrix[i][j] != 0) 
nonZero++; 
int sparse[nonZero][3]; 
int k = 0; 
for(int i = 0; i < rows; i++) { for(int j = 0; j < cols; j++) { if(matrix[i][j] != 0) 
{ sparse[k][0] = i;
sparse[k][1] = j sparse[k][2] = matrix[i][j]; 
k++; } } } 
printf("\nSparse Matrix Representation (row, column, value):\n"); 
for(int i = 0; i < nonZero; i++) { printf("%d\t%d\t%d\n", sparse[i][0], sparse[i][1], sparse[i][2]); } return 0;}

14)Polynomial representation

 Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Term { 
int coeff; 
int exp; 
struct Term* next; };
 struct Term* createTerm(int coeff, int exp) 
{ struct Term* newTerm = (struct Term*)malloc(sizeof(struct Term)); newTerm->coeff = coeff; 
newTerm->exp = exp; 
newTerm->next = NULL; 
return newTerm; } 
void insertTerm(struct Term** head, int coeff, int exp) 
{ struct Term* newTerm = createTerm(coeff, exp); 
if(*head == NULL)
 { *head = newTerm; 
return; } 
struct Term* temp = *head; while(temp->next != NULL)
 temp = temp->next; 
temp->next = newTerm; } 
void displayPolynomial(struct Term* head) 
{ struct Term* temp = head; while(temp != NULL) { printf("%dx^%d", temp->coeff, temp->exp); 
if(temp->next != NULL) 
printf(" + "); 
temp = temp->next; }
 printf("\n"); } 
int main() 
{ struct Term* poly = NULL; 
int n, coeff, exp;
 printf("Enter number of terms in the polynomial: "); 
scanf("%d", Cn); 
for(int i = 0; i < n; i++) { printf("Enter coefficient and exponent of term %d: ", i+1); scanf("%d %d", Ccoeff, Cexp); insertTerm(Cpoly, coeff, exp); } printf("\nPolynomial: "); displayPolynomial(poly);
 return 0; } 

15)Creation of binary tree

 Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node* left; 
struct Node* right; };
 struct Node* createNode(int value) { struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->data = value; 
newNode->left = NULL; 
newNode->right = NULL; 
return newNode; } 
void displayTree(struct Node* root) { if(root != NULL) { displayTree(root->left); printf("%d ", root->data); displayTree(root->right); } } 
int main() 
{ struct Node* root = createNode(1); root->left = createNode(2); root->right = createNode(3); root->left->left = createNode(4); root->left->right = createNode(5); printf("Binary Tree (Inorder Traversal): "); 
displayTree(root); 
printf("\n"); 
return 0; } 

16)Binary tree using array 

Program: 
#include <stdio.h> 
int main() 
{ int n; 
printf("Enter number of nodes in the binary tree: "); 
scanf("%d", Cn); 
int tree[n]; 
printf("Enter %d elements:\n", n); for(int i = 0; i < n; i++) { scanf("%d", Ctree[i]); } printf("\nBinary Tree (Level Order): "); 
for(int i = 0; i < n; i++) { printf("%d ", tree[i]); } printf("\n"); 
printf("\nParent -> Left Child, Right Child\n"); 
for(int i = 0; i < n; i++) 
{ int left = 2*i + 1; 
int right = 2*i + 2; 
printf("%d -> ", tree[i]); 
if(left < n) 
printf("%d ", tree[left]); 
else printf("NULL "); 
if(right < n) 
printf("%d", tree[right]); 
else 
printf("NULL");
 printf("\n"); } 
return 0; } 

17)Binary tree using queues 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
#define MAX 100 
struct Node { 
int data; 
struct Node* left; 
struct Node* right; 
}; 
struct Node* queue[MAX]; 
int front = 0, rear = 0; 
void enqueue(struct Node* node) { queue[rear++] = node; } 
struct Node* dequeue() { 
return queue[front++]; } 
int isEmpty() {
 return front == rear; } 
struct Node* createNode(int value) { struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->data = value; 
newNode->left = newNode->right = NULL; 
return newNode; } 
void inorder(struct Node* root) { if(root != NULL) { inorder(root->left); 
printf("%d ", root->data); inorder(root->right); } } 
int main() 
{ int value; 
printf("Enter root node value: "); scanf("%d", Cvalue); 
struct Node* root = createNode(value); 
enqueue(root); 
while(!isEmpty()) 
{ struct Node* temp = dequeue(); 
int leftVal, rightVal; 
printf("Enter left child of %d (-1 for no child): ", temp->data); scanf("%d", CleftVal); 
if(leftVal != -1) 
{ temp->left = createNode(leftVal); enqueue(temp->left); } 
printf("Enter right child of %d (-1 for no child): ", temp->data); scanf("%d", CrightVal); if(rightVal != -1) 
{ temp->right = createNode(rightVal); enqueue(temp->right); } } printf("\nBinary Tree (Inorder Traversal): "); 
inorder(root); 
printf("\n"); 
return 0; } 

18) Insertion and deletion of nodes operations of Binary tree 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node 
{ int data; 
struct Node* next; }; 
void insertAtBeginning(struct Node** head, int value) 
{ struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->data = value; 
newNode->next = *head; 
*head = newNode; 
printf("%d inserted at beginning.\n", value); } 
void insertAtEnd(struct Node** head, int value) 
{ struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->data = value; 
newNode->next = NULL; 
if(*head == NULL)
 { *head = newNode;
 printf("%d inserted at end.\n", value); 
return; } 
struct Node* temp = *head; while(temp->next != NULL)
 temp = temp->next; 
temp->next = newNode; 
printf("%d inserted at end.\n", value); }
 void deleteNode(struct Node** head, int value) 
{ struct Node* temp = *head; 
struct Node* prev = NULL; 
if(temp != NULL CC temp->data == value) 
{ *head = temp->next; 
free(temp); 
printf("%d deleted.\n", value); return;} 
while(temp != NULL CC temp->data != value) 
{ prev = temp; temp = temp->next; } if(temp == NULL) 
{ printf("%d not found.\n", value); return; } 
prev->next = temp->next; 
free(temp); 
printf("%d deleted.\n", value); } void display(struct Node* head) { if(head == NULL) 
{ printf("List is empty.\n"); return; } 
struct Node* temp = head; printf("Linked List: "); while(temp != NULL) 
{ printf("%d -> ", temp->data); 
temp = temp->next; } printf("NULL\n"); 
} 
int main() 
{ struct Node* head = NULL; 
int choice, value; 
do { 
printf("\n--- Linked List Operations ---\n"); 
printf("1. Insert at beginning\n2. Insert at end\n3. Delete node\n4. Display\n5. Exit\n"); 
printf("Enter choice: "); scanf("%d", Cchoice); 
switch(choice) 
{ case 1: printf("Enter value to insert: "); 
scanf("%d", Cvalue); insertAtBeginning(Chead, value); break; 
case 2: printf("Enter value to insert: "); 
scanf("%d", Cvalue); insertAtEnd(Chead, value); 
break; 
case 3: printf("Enter value to delete: "); 
scanf("%d", Cvalue); deleteNode(Chead, value); 
break; 
case 4: display(head); 
break; 
case 5:printf("Exiting...\n"); break; 
default: printf("Invalid choice.\n"); } } 
while(choice != 5); 
return 0; } 

19) Breadth First Search(BFS)

 Program: 
#include <stdio.h> 
#define MAX 100 
void bfs(int graph[MAX][MAX], int n, int start) 
{ int visited[MAX] = {0}; 
int queue[MAX], front = 0, rear = 0; visited[start] = 1; 
queue[rear++] = start; 
printf("BFS traversal: "); while(front != rear) 
{ int node = queue[front++]; printf("%d ", node); 
for(int i = 0; i < n; i++) { if(graph[node][i] CC !visited[i]) { queue[rear++] = i; 
visited[i] = 1; } } } printf("\n"); } 
int main() 
{ int n, edges; 
printf("Enter number of nodes: "); 
scanf("%d", Cn); 
printf("Enter number of edges: "); scanf("%d", Cedges); 
int graph[MAX][MAX] = {0}; 
int u, v; 
printf("Enter edges (u v) 0-indexed:\n"); 
for(int i = 0; i < edges; i++) { scanf("%d %d", Cu, Cv); 
graph[u][v] = 1; 
graph[v][u] = 1; 
 } int start; 
printf("Enter starting node: "); scanf("%d", Cstart); 
bfs(graph, n, start); 
return 0; } 

20)Depth First Search(DFS) 

Program: 
#include <stdio.h> 
#define MAX 100 
void dfs(int graph[MAX][MAX], int n, int start) 
{ int visited[MAX] = {0}; 
int stack[MAX]; 
int top = -1; 
stack[++top] = start; 
printf("DFS traversal: "); while(top != -1) 
{ int node = stack[top--]; 
if(!visited[node]) 
{ printf("%d ", node); 
visited[node] = 1; } 
for(int i = n-1; i >= 0; i--)
 {  if(graph[node][i] CC !visited[i]) 
{ stack[++top] = i; }}} printf("\n"); } 
int main() 
{ int n, edges; 
printf("Enter number of nodes: "); 
scanf("%d", Cn); 
printf("Enter number of edges: "); scanf("%d", Cedges); 
int graph[MAX][MAX] = {0}; 
int u, v; 
printf("Enter edges (u v) 0-indexed:\n"); 
for(int i = 0; i < edges; i++) { scanf("%d %d", Cu, Cv); 
graph[u][v] = 1; graph[v][u] = 1;  } int start; 
printf("Enter starting node: "); scanf("%d", Cstart); 
dfs(graph, n, start); 
return 0; } 

21)The address of the pointer

 Program: 
#include <stdio.h> 
int main() 
{ int x = 10;        
int *ptr = &x; 
printf("Address of pointer ptr: %p\n", (void*)&ptr); 
printf("Address stored in ptr (address of x): %p\n", (void*)ptr);  return 0; } 

22)Initialization of calloc() function into 0  

Program:  
#include <stdio.h>  
#include <stdlib.h>  
int main() 
{      
int n = 5;      
int *ptr;     
ptr = (int *)calloc(n, sizeof(int));    if (ptr == NULL)  
{  printf("Memory not allocated\n");                 return 1;    }           printf("Values after calloc allocation:\n");           
for (int i = 0; i < n; i++)  {             
 printf("ptr[%d] = %d\n", i, ptr[i]);   }               free(ptr);
 return 0; }  

23)Time taken by arrays and linked lists during Insertion and deletion.

 Program: 
#include <stdio.h> 
#include <stdlib.h> 
#include <time.h> 
struct Node {     
int data;     
struct Node* next; }; 
void insertLinkedList(struct Node** head, int value)
 {     
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));     newNode->data = value;     newNode->next = *head;     
*head = newNode; } 
void deleteLinkedList(struct Node** head) {     
if (*head == NULL)         
return;     
struct Node* temp = *head;     
*head = (*head)->next;     free(temp); } 
int main() {     
int n = 100000;     
int *arr = (int*)malloc(n * sizeof(int));     
struct Node* head = NULL;     clock_t start, end;     
double time_taken;     
start = clock();     
for (int i = 0; i < n; i++) { 
for (int j = i; j > 0; j--)             arr[j] = arr[j - 1];         
arr[0] = i;}     
end = clock();     
time_taken = ((double)(end - start))      
printf("Array insertion at beginning: %f seconds\n", time_taken);     
start = clock();     
for (int i = 0; i < n; i++) {         
for (int j = 0; j < n - i - 1; j++)             arr[j] = arr[j + 1];}     
end = clock();     
time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;     printf("Array deletion from beginning: %f seconds\n", time_taken);     
start = clock();     
for (int i = 0; i < n; i++)         insertLinkedList(&head, i);     
end = clock();     
time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;     printf("Linked list insertion at beginning: %f seconds\n", time_taken);      
start = clock();     
for (int i = 0; i < n; i++)         deleteLinkedList(&head);     
end = clock();     time_taken = ((double)(end - start)) / CLOCKS_PER_SEC;     
printf("Linked list deletion from beginning: %f seconds\n", time_taken);     
free(arr);     
return 0; } 

24)Level order 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node *left, *right; }; 
struct Node* newNode(int val) { struct Node* n = (struct Node*)malloc(sizeof(struct Node)); n->data = val; 
n->left = n->right = NULL; 
return n; } 
struct Node* queue[20]; 
int front = 0, rear = -1; 
void enqueue(struct Node* node) { 
queue[++rear] = node; } 
struct Node* dequeue() {     
return queue[front++]; } 
void levelOrder(struct Node* root) {     
if (root == NULL)         
return;     
enqueue(root);     
while (front <= rear) {         
struct Node* temp = dequeue();         printf("%d ", temp->data);         if (temp->left)             enqueue(temp->left);         
if (temp->right)             enqueue(temp->right);} } 
int main() {     
struct Node* root = newNode(1);     root->left = newNode(2);     root->right = newNode(3);     root->left->left = newNode(4);     root->left->right = newNode(5);     printf("Level Order Traversal: ");     levelOrder(root);     
return 0; 

25)DFS and BFS using adjacency list

 Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int vertex; 
struct Node* next; }; 
struct Node* adj[10]; 
int visited[10];
 int n; 
struct Node* createNode(int v) { struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->vertex = v; 
newNode->next = NULL; 
return newNode; } 
void addEdge(int src, int dest) {     
struct Node* newNode = createNode(dest);     
newNode->next = adj[src];     adj[src] = newNode;     
newNode = createNode(src);     newNode->next = adj[dest];     adj[dest] = newNode; } 
void DFS(int v) {     
struct Node* temp = adj[v];     printf("%d ", v);     
visited[v] = 1;     
while (temp != NULL) {        
 if (!visited[temp->vertex])             DFS(temp->vertex);         
temp = temp->next;
     } } 
void BFS(int start) {    
 int queue[10], front = 0, rear = -1;     
struct Node* temp;     visited[start] = 1;     
queue[++rear] = start;     
while (front <= rear) {         
int v = queue[front++];         printf("%d ", v);         
temp = adj[v]; 
   while (temp != NULL) {             
if (!visited[temp->vertex]) {                 
visited[temp->vertex] = 1;                 queue[++rear] = temp->vertex;}             temp = temp->next;}} } 
int main() {     
int i, edges, u, v, start;     printf("Enter number of vertices: ");     
scanf("%d", &n);     
for (i = 0; i < n; i++)         adj[i] = NULL;     
printf("Enter number of edges: ");     scanf("%d", &edges);      
for (i = 0; i < edges; i++) {         
scanf("%d %d", &u, &v);         addEdge(u, v);     }     printf("Enter starting vertex: ");     scanf("%d", &start);     
for (i = 0; i < n; i++)         visited[i] = 0;     
printf("DFS: "); 
DFS(start); 
for (i = 0; i < n; i++) 
visited[i] = 0; 
printf("\nBFS: "); 
BFS(start); 
return 0; } 

26)Circular linked list operation

 Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node* next; };
 struct Node* head = NULL; 
void insert(int val) { 
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));     newNode->data = val;     
if (head == NULL) {         
head = newNode;         newNode->next = head;         return;}     
struct Node* temp = head;     
while (temp->next != head)         temp = temp->next;     
temp->next = newNode;     newNode->next = head; } 
void deleteNode(int key) {     
struct Node *temp = head, *prev = NULL;     
if (head == NULL)         
return;     
if (head->data == key) {         
while (temp->next != head)             temp = temp->next;         
if (temp == head) {             
free(head);             
head = NULL;         
} else {             
temp->next = head->next;             free(head);             
head = temp->next;
 }         
return;     
}     
prev = head;     
temp = head->next;     
while (temp != head && temp->data != key) {         
prev = temp;         
temp = temp->next;     }     
if (temp->data == key) {         
prev->next = temp->next;         free(temp);} } 
void display() {     
if (head == NULL)        
 return;     
struct Node* temp = head;     
do {         
printf("%d ", temp->data);         temp = temp->next;} 
while (temp != head); } 
int main() {     
insert(10);     
insert(20);     
insert(30); 
printf("Circular List: "); display(); 
deleteNode(20); 
printf("\nAfter deletion: "); display(); 
return 0; }  

27)Comparison of two strings using built in function 

Program: 
#include <stdio.h>
#include <stdlib.h> 
#include <string.h> 
int main() { 
char str1[50], str2[50]; printf("Enter first string: "); 
scanf("%s", str1); 
printf("Enter second string: "); scanf("%s", str2); 
if (strcmp(str1, str2) == 0) printf("Strings are equal"); 
else 
printf("Strings are not equal"); return 0; } 

28)Linked list insertion in the middle and deletion in the middle 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node* next; 
}; struct Node* insertEnd(struct Node* head, int val) {     
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));     newNode->data = val;     newNode->next = NULL;     
if (head == NULL)         
return newNode;     
struct Node* temp = head;     
while (temp->next)         
temp = temp->next;     
temp->next = newNode;     
return head; } 
struct Node* insertMiddle(struct Node* head, int val) {     
struct Node *slow = head, *fast = head;     
struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));     newNode->data = val;     
if (head == NULL){         
newNode->next = NULL;         
return newNode;     }     
while (fast && fast->next)     {         
fast = fast->next->next;
   slow = slow->next;     }     newNode->next = slow->next;     slow->next = newNode;     
return head; } 
struct Node* deleteMiddle(struct Node* head) {     
struct Node *slow = head, *fast = head, *prev = NULL;     
if (head == NULL || head->next == NULL)         
return NULL;    
 while (fast && fast->next){         
fast = fast->next->next;         prev = slow;         
slow = slow->next;     }      prev->next = slow->next;     free(slow);     
return head; } 
void display(struct Node* head) {     while (head)     {         printf("%d -> ", head->data);
head = head->next; } printf("NULL\n"); } int main() { } struct Node* head = NULL; head = insertEnd(head, 10); head = insertEnd(head, 20); head = insertEnd(head, 30); head = insertEnd(head, 40); printf("Original list: "); display(head); head = insertMiddle(head, 25); printf("After insertion at middle: "); 
display(head); 
head = deleteMiddle(head); printf("After deletion at middle: "); 
display(head); 
 return 0; } 

29)Traversal binary matrix 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int data; 
struct Node *left, *right; }; 
struct Node* newNode(int val) { struct Node* node = (struct Node*)malloc(sizeof(struct Node)); node->data = val; 
node->left = node->right = NULL; return node; } 
void inorder(struct Node* root) 
{ if (root == NULL) 
return; 
inorder(root->left); 
printf("%d ", root->data); inorder(root->right); } 
void preorder(struct Node* root) { if (root == NULL) 
return; 
printf("%d ", root->data); preorder(root->left); preorder(root->right); }
 void postorder(struct Node* root) { if (root == NULL) 
return; 
postorder(root->left); postorder(root->right);
 printf("%d ", root->data); } 
int main() { 
struct Node* root = newNode(1); root->left = newNode(2); butqroot->right = newNode(3); root->left->left = newNode(4); root->left->right = newNode(5); printf("Inorder Traversal: "); inorder(root); 
printf("\nPreorder Traversal: "); preorder(root); 
printf("\nPostorder Traversal: "); postorder(root); 
return 0; } 

30)Sparse matrix using linked list 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
struct Node { 
int row, col, value; 
struct Node* next; }; 
struct Node* head = NULL; 
void insert(int r, int c, int val) { struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); newNode->row = r; 
newNode->col = c;     
newNode->value = val;     newNode->next = NULL;     
if (head == NULL) {         
head = newNode;         
return;}     
struct Node* temp = head;     
while (temp->next != NULL)         temp = temp->next;     
temp->next = newNode; } 
void display() {     
struct Node* temp = head;     printf("Row  Col  Value\n");     while (temp != NULL) {         
printf("%d    %d    %d\n", temp->row, temp->col, temp->value);         temp = temp->next;     } } 
int main() {     
int m, n, i, j, val;     printf("Enter rows and columns: ");     scanf("%d %d", &m, &n);     printf("Enter matrix elements:\n");     for (i = 0; i < m; i++) {         
for (j = 0; j < n; j++) { 
 scanf("%d", &val);             
if (val != 0)                 insert(i, j, val);}}     printf("\nSparse Matrix (Linked List Representation):\n");     
display();     
return 0; } 

31)Check for modulo division, queue full and queue empty for circular queues 

Program: 
#include <stdio.h> 
#include <stdlib.h> 
#define SIZE 5 
int queue[SIZE]; 
int front = -1, rear = -1; int isFull() {     
return ((rear + 1) % SIZE == front); } 
int isEmpty() {     
return (front == -1); } 
void enqueue(int value) {     
if (isFull()){         
printf("Queue is Full\n");         return;     }     
if (front == -1)         
front = 0;     
rear = (rear + 1) % SIZE;     queue[rear] = value;     printf("Inserted %d\n", value); } void dequeue() {     
if (isEmpty())     
{printf("Queue is Empty\n");         return;     }     
printf("Deleted %d\n", queue[front]);     
if (front == rear)         
front = rear = -1;     
else         
front = (front + 1) % SIZE; } 
void display() {     
int i;     
if (isEmpty())     {         
printf("Queue is Empty\n");         return;     }     
printf("Queue elements: ");     
i = front;     
while (i != rear)     {         
printf("%d ", queue[i]);         
i = (i + 1) % SIZE;     }     printf("%d\n", queue[i]); } 
int main() 
{  
enqueue(10); 
enqueue(20); 
enqueue(30); 
enqueue(40); 
enqueue(50); 
display(); 
dequeue(); 
dequeue(); 
enqueue(60); 
enqueue(70); 
display(); 
return 0;
} 