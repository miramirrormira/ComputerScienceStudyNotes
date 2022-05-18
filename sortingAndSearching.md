# Sorting and Searching

## Binary Search Algorithm
A binary search algorithm finds an item in a sorted list in O(lg(n))O(lg(n)) time.

A brute force search would walk through the whole list, taking O(n)O(n) time in the worst case.


## Sorting
### bubble sort

### merge sort
| average |  worst  |  memory   |
| ------- | ------- | --------- |
| O(nlogn)| O(nlogn)|   O(n)    |

merge sort is stable
[Why is merge sort's space complexity O(n) not O(nlog(n))?](https://stackoverflow.com/a/28641693/4285900)

#### Why MergeSort is preferred over QuickSort for Linked Lists? 
In case of linked lists the case is different mainly due to difference in memory allocation of arrays and linked lists. Unlike arrays, linked list nodes may not be adjacent in memory. Unlike array, in linked list, we can insert items in the middle in O(1) extra space and O(1) time. Therefore merge operation of merge sort can be implemented without extra space for linked lists.
In arrays, we can do random access as elements are continuous in memory. Let us say we have an integer (4-byte) array A and let the address of A[0] be x then to access A[i], we can directly access the memory at (x + i*4). Unlike arrays, we can not do random access in linked list. Quick Sort requires a lot of this kind of access. In linked list to access i’th index, we have to travel each and every node from the head to i’th node as we don’t have continuous block of memory. Therefore, the overhead increases for quick sort. Merge sort accesses data sequentially and the need of random access is low. 

### quick sort
| average | worst   | memory  |
| ------- | ------- | ------- |
| O(nlogn)| $O(n^2)$  | O(logn) |

Worst case happens when the array is already sorted, and the partitioning doesn't divide the array
Best case happens when the partitioning always chose the element that's equal to the median. 

quick sort is unstable

#### Why Quick Sort is preferred over MergeSort for sorting Arrays? 
Quick Sort in its general form is an in-place sort (i.e. it doesn’t require any extra storage) whereas merge sort requires O(N) extra storage, N denoting the array size which may be quite expensive. Allocating and de-allocating the extra space used for merge sort increases the running time of the algorithm. Comparing average complexity we find that both type of sorts have O(NlogN) average complexity but the constants differ. For arrays, merge sort loses due to the use of extra O(N) storage space.
Most practical implementations of Quick Sort use randomized version. The randomized version has expected time complexity of O(nLogn). The worst case is possible in randomized version also, but worst case doesn’t occur for a particular pattern (like sorted array) and randomized Quick Sort works well in practice.
Quick Sort is also a cache friendly sorting algorithm as it has good locality of reference when used for arrays.
Quick Sort is also tail recursive, therefore tail call optimizations is done.

[Hoares vs Lomuto partition scheme](https://www.geeksforgeeks.org/hoares-vs-lomuto-partition-scheme-quicksort/?ref=rp)

### bucket sort

### radix sort


## [Stability](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/)
A sorting algorithm is stable if the two objects with equal keys appear in the same order in sorted output as they appear in the input array to be sorted. Stability means that equivalent elements retain their relative positions after sorting.

### when do we care about stability
When equal elements are indistinguishable, such as with integers, or more generally, any data where the entire element is the key, stability is not an issue. Stability is also not an issue if all keys are different.
