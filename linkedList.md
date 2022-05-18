# Linked List
Linked list is a linear data structure, in which the elements are stored not in a contiguous memory locations, but are linked using pointers.
Linked list consists of nodes where each node contains a data field and a reference to the next node.


accessing the n th node of a linked list requires iterating over the first n-1 elements

|         | Worst Case | 
| ------- | ---------- | 
| insert  | O(1)       | 
| delete  | O(1)       |
| search  | O(n)       |

## Doubly Linked List (DLL)
A doubly linked list contains an extra pointer, typically called a previous pointer.
```
class Node:
    def __init__(self, data, next = None, prev = None):
        self.data = data
        self.next = next
        self.prev = prev
```

### Insertion
1. add a node at the front
   The new node is always added before the head of the given linked list. The newly added node becomes the new head of DLL. For example, if the given linked list is 102, and we add an item 5 at the front, then the linked list becomes 5102.
    ```
    def push(self, new_data):

        new_node = Node(data = new_data)
        new_node.next = self.head
        new_node.prev = None

        if self.head is not None:
            self.head.prev = new_node
        
        self.head = new_node
    ```

2. add a node after a given node
   We are given a pointer to a node as prev_node, and the new node is inserted after the given node.
   ```
    def insertAfter(self, prev_node, new_data):
        if prev_node is None:
            print("This node doesn't exist in DLL")
            return

        new_node = Node(data=new_data)

        new_node.next = prev_node.next
        prev_node.next = new_node
        new_node.prev = prev_node

        if new_node.next is not None:
            new_node.next.prev = new_node
   ```
3. add a node at the end
   The new node is added after the last node of the given linked list. For example if the given DLL is 102, and we add an item 5 at the end, then the DLL becomes 1025.
   Since a linked list is typically represented by the head of it, we have to traverse the list till the end and then change the next pointer of the last node to the new node.
   
