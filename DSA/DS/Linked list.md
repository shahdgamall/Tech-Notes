[source: ](https://youtu.be/Nq7ok-OyEpg?si=fH53pEh3Hy2m5rBn)
#### What is a Linked List?
- A linked list is a data structure that stores elements, similar to an array, but unlike arrays, elements in a linked list are not stored in contiguous memory locations.
- The size of a linked list can be increased or decreased dynamically at any moment.
- Each element (node) in a linked list contains two things: the data itself and a pointer (or reference) to the next element in the sequence.
- The first node of a linked list is called the head, and the last node is called the tail. The 'next' pointer of the tail node points to null (or null pointer).
- ### head:
  the head of a linked list is of paramount importance because it serves as the entry point to the entire data structure. Without a reference to the head node, there is no way to locate any of the other elements within the list
- Quote: "link list is a similar data structure but the difference is they're not in contiguous location yes they're not in contiguous location."

#### Memory Allocation:
- Linked list nodes are allocated in the Heap memory, and their locations are not necessarily adjacent.
- Quote: "...they stored in the Heap memory in like it's not a contiguous location..."
#### Traversal:
- Unlike arrays where elements can be accessed directly by index, linked lists are traversed sequentially starting from the head.
- Traversal is achieved by following the 'next' pointer of each node.
- Quote: "...in order to go to the next one you go to this element and you say where is the next he says at M2 so you straight away go to M2 straight away go to that memory location and access that element."
- The traversal continues until the 'next' pointer of a node is null, indicating the end of the list (the tail).
#### Use Cases:
- Linked lists are used in various applications where dynamic resizing is required, such as in the implementation of stacks and queues.
- A browser's back and forward button functionality is presented as a practical example of a linked list, where each visited page can be considered a node, and the back/forward actions move through the linked sequence.
- the concept of a 1D linked list where each element remembers only the 'next' element. It gives the browser history as a real-life example.
  the functionality of both back and forward buttons implies the existence of a mechanism to track both the next and the previous pages visited. This type of bidirectional movement is characteristic of a doubly linked list, where each node has pointers to both the next and the previous node.
-  Quote: "looks like a link list you don't know the size initially how how many things will you be searching how many things will you be going deep into and you can always come back as much as you want you can always go as much as you want so perfect example where link list is used"
---
#### Node Structure (Struct/Class):
- To represent a node in a linked list, a self-defined data type (using struct in C++ or class in C++ and Java) is required.
- This structure typically contains:
	- data: To store the value of the element.
	- next: A pointer (in C++) or reference (in Java) to the next node of the same self-defined data type.
```c++
C++ Example:
struct node {
    int data;
    node* next;
    node(int data1, node* next1) {
        data = data1;
        next = next1;
    }
};
```
```java
Java Example:
 class Node {
    int data;
    Node next;
    Node(int data1) {
        data = data1;
        next = null;
    }
}
```
- The source emphasizes the use of class over struct in professional settings to leverage object-oriented programming concepts.
- Constructors are used to initialize the data and next fields of a node when a new node is created.
- The new keyword in C++ (and Java) is used to allocate memory for a new node in the Heap, and it returns a pointer (or reference) to that memory location.
#### Converting an Array to a Linked List:
- The process involves iterating through the array and creating a new node for each element.
- The first element of the array becomes the head of the linked list.
- A mover (or temporary pointer) is used to traverse the linked list as new nodes are created and linked to the end.
- The 'next' pointer of the previously created node is set to point to the newly created node.
- The head of the linked list is returned as the starting point.
#### Traversal Implementation:
- A temporary pointer is initialized to the head of the linked list.
- A while loop continues as long as the temporary pointer is not null.
  that is why we didn't use the for loop because it is used most of time when we know the number of elements, in linked list we don't know.
- Inside the loop, the data of the current node is accessed (e.g., printed), and the temporary pointer is moved to the next node using temp = temp->next (in C++) or temp = temp.next (in Java).
``` c++
void traverse()
    {
         //temp is a pointer to the first node
         //we can't use head to traverse the linked list because we will lose the head pointer
         //so we use a temporary pointer to traverse the linked list
            node *temp = head;
            while(temp != nullptr)
            {
                cout << temp->data << " ";
                temp = temp->next;
            }
        }
```
#### Length of a Linked List:
- The length is determined by traversing the entire linked list and maintaining a counter.
- The counter is incremented for each node visited until the end of the list (null) is reached.
- The final value of the counter represents the length of the linked list.
- Time complexity: O(n), where n is the number of nodes.
``` c++
int len()
        {
            int cnt = 0;
            node *temp = head;
            while(temp != nullptr)
            {
                cnt++;
                temp = temp->next;
            }
            return cnt;
        }
```
#### Searching for an Element in a Linked List:
- The list is traversed starting from the head.
- At each node, the data is compared with the element being searched for.
- If a match is found, a Boolean true (or 1) is returned.
- If the entire list is traversed without finding the element, false (or 0) is returned.
- Time complexity: O(n) in the worst case (element not found or at the end), O(1) in the best case (element is the head), and O(n/2) on average.







