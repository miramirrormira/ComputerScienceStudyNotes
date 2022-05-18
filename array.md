# Array


1. An array organizes items of the same type sequentially, one after another in memory.
2. Each position in the array has an index, starting at 0.
3. Array can hold up to N items. N is decided by the programmer
4. Adding a new item to an array that is already full requires creating a new array of size N+1, and copying every item from the old array to the new one


**Advantage**
- Fast lookups. Retrieving the element at a given index takes O(1) time, regardless of the length of the array.
- Fast appends. Adding a new element at the end of the array takes O(1) time, if the array has space.

**Disadvantage**
- Fixed size. 
- Costly inserts and deletes. You have to "scoot over" the other elements to fill in or close gaps, which takes worst-case O(n) time.


|        | Time Complexity |
| ------ | ---- |
| space  | O(n) |
| lookup | O(1) |
| append | O(1) |
| insert | O(n) |
| delete | O(n) |
| slicing| O(n) |

### Inserting
1. make space by "scooting over" everything starting at the index we're inserting into
2. insertht element at the index

### Deleting
1. delete element at the index
2. fill the gap - "scooting over" all the elements after the deleted element

### Slicing
```
my_list[start_index:end_index]
```
This takes O(n) time and O(n) space, where n is the number of elements in the resulting list.
1. allocating a new list
2. copying the elements from the original list to the new list

## Applications on Array

- Array stores data elements of the same data type.
- Used in solving matrices problem
- Applied as lookup table in computer.
- Databases record are also implemented by array.
- Helps in implementing sorting algorithm.
- Different variable of same type can be saved under one name.
- Arrays can be used for CPU scheduling.
- Used to Implement other data structures like Stacks, Queues, Heaps, Hash tables, etc.

