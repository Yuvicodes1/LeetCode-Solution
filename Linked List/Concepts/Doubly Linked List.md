# Doubly Linked List Tutorial

A doubly linked list is a more complex data structure than a singly linked list, but it offers several advantages. The main advantage of a doubly linked list is that it allows for efficient traversal of the list in both directions. This is because each node in the list contains a pointer to the previous node and a pointer to the next node. This allows for quick and easy insertion and deletion of nodes from the list, as well as efficient traversal of the list in both directions.

<img width="897" height="274" alt="image" src="https://github.com/user-attachments/assets/ae67e063-c7c1-4d92-9b30-bbf0acf46f51" />

## 1. CPP
```cpp
struct Node {

    // To store the Value or data.
    int data;

    // Pointer to point the Previous Element
    Node* prev;

    // Pointer to point the Next Element
    Node* next;
  
    // Constructor
    Node(int d) {
       data = d;
       prev = next = nullptr;      
    }
};
```

## 2. Python

```python
class Node:
  
    def __init__(self, data):
        # To store the value or data.
        self.data = data

        # Reference to the previous node
        self.prev = None

        # Reference to the next node
        self.next = None
```
