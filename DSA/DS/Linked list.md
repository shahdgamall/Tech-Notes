[source: ](https://youtu.be/Nq7ok-OyEpg?si=fH53pEh3Hy2m5rBn)
### What is a Linked List?
- A linked list is a data structure that stores elements, similar to an array, but unlike arrays, elements in a linked list are not stored in contiguous memory locations.
- The size of a linked list can be increased or decreased dynamically at any moment.
- Each element (node) in a linked list contains two things: the data itself and a pointer (or reference) to the next element in the sequence.
- The first node of a linked list is called the head, and the last node is called the tail. The 'next' pointer of the tail node points to null (or null pointer).
- #### head:
  the head of a linked list is of paramount importance because it serves as the entry point to the entire data structure. Without a reference to the head node, there is no way to locate any of the other elements within the list
- Quote: "link list is a similar data structure but the difference is they're not in contiguous location yes they're not in contiguous location."

### Memory Allocation:
- Linked list nodes are allocated in the Heap memory, and their locations are not necessarily adjacent.
- Quote: "...they stored in the Heap memory in like it's not a contiguous location..."
### Traversal:
- Unlike arrays where elements can be accessed directly by index, linked lists are traversed sequentially starting from the head.
- Traversal is achieved by following the 'next' pointer of each node.
- Quote: "...in order to go to the next one you go to this element and you say where is the next he says at M2 so you straight away go to M2 straight away go to that memory location and access that element."
- The traversal continues until the 'next' pointer of a node is null, indicating the end of the list (the tail).
### Use Cases:
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
```c++
bool searchElement(Node* head, int targetValue){
    // Start from the head of the list
    Node* currentNode = head;

    // Traverse the list as long as the current node is not null
    while (currentNode != nullptr) {
        // Check if the data in the current node matches the target value
        if (currentNode->data == targetValue) {
            // Element found, return true
            return true;
        }
        // Move to the next node in the list
        currentNode = currentNode->next;
    }

    // If the loop completes without finding the element, it's not present
    return false;
}
```
### deletion and insertion:
#### Deletion of the Head:
- To delete the head, the head pointer needs to be moved to the next node.
- In C++, the memory occupied by the original head node must be manually freed using free(temp) or delete temp, where temp is a pointer to the original head.
- In Java, the garbage collector automatically reclaims the memory of the unreferenced original head node.
- Edge case: If the list is empty (head is null), nothing needs to be done, and the null head is returned.
```c++
Code snippet (C++):

Node* removeHead(Node* head) {
    if (head == nullptr) {
        return head;
    }
    Node* temp = head;
    head = head->next;
    delete temp; // or free(temp);
    return head;
}
```
```java
Code snippet (Java):
private static Node removeHead(Node head) {
    if (head == null) {
        return head;
    }
    head = head.next;
    return head;
}
```
#### Deletion of the Tail:
- To delete the tail, you need to traverse the list to stop at the second-to-last element.
- The next pointer of the second-to-last element should then be set to null.
- The memory occupied by the original tail node needs to be freed in C++.
- Edge cases:
	- If the list is empty or has only one element, after deleting the tail, the list becomes empty, so null is returned.
	- Traversal stops when temporary->next->next is null.
```c++
Code snippet (C++):
Node* deleteTail(Node* head) {
    if (head == nullptr || head->next == nullptr) {
        return nullptr;
    }
    Node* temp = head;
    while (temp->next->next != nullptr) {
        temp = temp->next;
    }
    delete temp->next; // or free(temp->next);
    temp->next = nullptr;
    return head;
}
```
```java
Code snippet (Java):
private static Node removeTail(Node head) {
    if (head == null || head.next == null) {
        return null;
    }
    Node temp = head;
    while (temp.next.next != null) {
        temp = temp.next;
    }
    temp.next = null;
    return head;
}
```
#### Deletion of the Kth Element:
- The goal is to delete the node at the Kth position (1-based indexing).
+ Edge case: If the list is empty, no deletion is possible.
+ If K is 1, it's the same as deleting the head.
- Traverse the list to reach the (K-1)th node.
- Update the next pointer of the (K-1)th node to point to the (K+1)th node, effectively skipping the Kth node.
- Free the memory of the Kth node in C++.
- If K is greater than the length of the list, no deletion occurs.
```c++
Code snippet (C++):
Node* removeK(Node* head, int K) {
    if (head == nullptr) {
        return head;
    }
    if (K == 1) {
        Node* temp = head;
        head = head->next;
        delete temp;
        return head;
    }
    Node* temp = head;
    Node* previous = nullptr;
    int count = 1;
    while (temp != nullptr && count < K) {
        previous = temp;
        temp = temp->next;
        count++;
    }
    if (temp == nullptr) {
        return head; // K is out of bounds
    }
    previous->next = temp->next;
    delete temp;
    return head;
}
```
#### Deletion by Value:
- The goal is to delete the first node with a specific value.
- Edge case: If the list is empty, no deletion is possible.
- If the head node's data matches the value, delete the head (similar to the first case).
- Traverse the list, keeping track of the previous node.
- When a node with the matching value is found, update the next pointer of the previous node to skip the current node.
- Free the memory of the deleted node in C++.
- A flag can be used to track if the element was found and deleted.
```c++
 Node* removeElement(Node* head, int element) {
    if (head == nullptr) { // If the list is empty
        return head;
    }

    if (head->data == element) { // If the head node has the value
        Node* temp = head;
        head = head->next;
        free(temp); // Or delete temp;
        return head;
    }

    Node* temp = head;
    Node* prev = nullptr;
    bool found = false;

    while (temp != nullptr && temp->next != nullptr) { // Traverse until the second to last node
        if (temp->next->data == element) {
            Node* nodeToDelete = temp->next;
            temp->next = temp->next->next;
            free(nodeToDelete); // Or delete nodeToDelete;
            found = true;
            break;
        }
        temp = temp->next;
    }

    if (!found) {
        // Optional: Handle the case where the element is not found
        // You might print a message or return the original head
    }

    return head;
}
```
--- 
#### Insertion at the Head:
- Create a new node with the given value.
- Set the next pointer of the new node to point to the current head.
- Update the head pointer to point to the new node.
+ Time complexity: O(1).
```c++
Code snippet (C++):
Node* insertHead(Node* head, int val) {
    Node* temp = new Node(val);
    temp->next = head;
    return temp;
}
```
```java
Code snippet (Java):
private static Node insertHead(Node head, int val) {
    Node temp = new Node(val);
    temp.next = head;
    return temp;
}
```
#### Insertion at the Tail:
- Create a new node with the given value and its next pointer set to null.
- Edge case: If the list is empty, the new node becomes the head.
- Traverse the list to reach the last node (the one whose next pointer is null).
- Set the next pointer of the last node to point to the new node.
```c++
Code snippet (C++):
Node* insertTail(Node* head, int val) {
    Node* newNode = new Node(val);
    if (head == nullptr) {
        return newNode;
    }
    Node* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->next = newNode;
    return head;
}
```
```java
Code snippet (Java):
private static Node insertTail(Node head, int val) {
    Node newNode = new Node(val);
    if (head == null) {
        return newNode;
    }
    Node temp = head;
    while (temp.next != null) {
        temp = temp.next;
    }
    temp.next = newNode;
    return head;
}
```
#### Insertion at the Kth Position:
- Create a new node with the given value.
- Edge case: If the list is empty, insertion is only possible at K=1.
- If K is 1, it's the same as inserting at the head.
- Traverse the list to reach the (K-1)th node.
- Set the next pointer of the new node to point to the current Kth node (temp->next).
- Set the next pointer of the (K-1)th node (temp) to point to the new node.
- If K is greater than the length of the list + 1, the insertion might be considered invalid depending on the requirements. The provided code seems to handle this by not performing the insertion.
```c++
Code snippet (C++):
Node* insertAtPosition(Node* head, int element, int K) {
    if (head == nullptr) {
        if (K == 1) {
            return new Node(element);
        } else {
            return head; // Or handle as error
        }
    }
    if (K == 1) {
        Node* newHead = new Node(element);
        newHead->next = head;
        return newHead;
    }
    Node* temp = head;
    int count = 1;
    while (temp != nullptr && count < K - 1) {
        temp = temp->next;
        count++;
    }
    if (temp == nullptr) {
        return head; // K is out of bounds
    }
    Node* newNode = new Node(element);
    newNode->next = temp->next;
    temp->next = newNode;
    return head;
}
```
####  Insertion Before a Value X:
- Create a new node with the given value.
- Edge case: If the list is empty, insertion is not possible before any value.
- If the head node's data matches the target value X, insert the new node at the head.
- Traverse the list, keeping track of the previous node.
- If the next node's data matches X, insert the new node between the current node and the next node.
```c++
Code snippet (C++):
Node* insertBeforeValue(Node* head, int element, int val) {
    if (head == nullptr) {
        return head;
    }
    if (head->data == val) {
        Node* newHead = new Node(element);
        newHead->next = head;
        return newHead;
    }
    Node* temp = head;
    while (temp->next != nullptr && temp->next->data != val) {
        temp = temp->next;
    }
    if (temp->next != nullptr) {
        Node* newNode = new Node(element);
        newNode->next = temp->next;
        temp->next = newNode;
    }
    return head;
}

```





