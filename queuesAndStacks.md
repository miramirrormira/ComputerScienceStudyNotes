# Queues

A queue stores items in a first-in, first-out (FIFO) order.

|         | Worst Case | 
| ------- | ---------- | 
| enqueue | O(1)       | 
| dequeue | O(1)       |
| peek    | O(1)       |
| space   | O(n)       |

## Uses:
- Breadth-first search uses a queue to keep track of the nodes to visit next

Not used for:
- Searchability is a weak spot for a Queue because it's designed tp only access both ends of it.

## Implementation
A queue can be implemented using a linked list. we maintain two pointers, front and rear. The front points the first item of queue and rear points to last item.
enQueue(): This operation adds a new node after rear and moves rear to the next node.
deQueue(): This operation removes the front node and moves front to the next node.


# Stack
A stack stores items in a last-in, first-out (LIFO) order.

|         | Worst Case | 
| ------- | ---------- | 
| enqueue | O(1)       | 
| dequeue | O(1)       |
| peek    | O(1)       |
| space   | O(n)       |

## Uses:
- The call stack is a stack that tracks function calls in a program. When a function returns, which function do we "pop" back to? The last one that "pushed" a function call.
- Depth-first search uses a stack (sometimes the call stack) to keep track of which nodes to visit next.
- String parsing—stacks turn out to be useful for several types of string parsing.