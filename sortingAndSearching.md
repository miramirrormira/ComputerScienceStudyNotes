# Sorting and Searching

## Binary Search Algorithm
A binary search algorithm finds an item in a sorted list in O(lg(n))O(lg(n)) time.

A brute force search would walk through the whole list, taking O(n)O(n) time in the worst case.


## Sorting
### bubble sort

### merge sort
| average | worst   | memory  |
| ------- | ------- | ------- |
| O(nlogn)| O(nlogn)| depends |

merge sort is stable

### quick sort
| average | worst   | memory  |
| ------- | ------- | ------- |
| O(nlogn)| O(n^2)  | O(logn) |

Worst case happens when the array is already sorted, and the partitioning doesn't divide the array
Best case happens when the partitioning always chose the element that's equal to the median. 

quick sort is unstable

### bucket sort

### radix sort


## [Stability](https://www.geeksforgeeks.org/stability-in-sorting-algorithms/)
A sorting algorithm is stable if the two objects with equal keys appear in the same order in sorted output as they appear in the input array to be sorted. Stability means that equivalent elements retain their relative positions after sorting.

### when do we care about stability
When equal elements are indistinguishable, such as with integers, or more generally, any data where the entire element is the key, stability is not an issue. Stability is also not an issue if all keys are different.
