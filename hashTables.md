# Hash tables

Hash tables combine the random access ability of an array with the dynamism of a linked list.

**Time Complexity**
|        | Average | Worst Case |
| ------ | ------- | ---------- |
| lookup | O(1)    | O(n)       |
| insert | O(1)    | O(n)       |
| delete | O(1)    | O(n)       |
| space  | O(n)    | O(n)       |

**Advantage**
- Fast lookups. Lookups take O(1)O(1) time on average.
- Flexible keys. Most data types can be used for keys, as long as they're hashable.

**Disadvantage**
- Slow worst-case lookups. Lookups take O(n)O(n) time in the worst case.
- Unordered. Keys aren't stored in a special order. If you're looking for the smallest key, the largest key, or all the keys in a range, you'll need to look through every key to find it.
- Single-directional lookups. While you can look up the value for a given key in O(1)O(1) time, looking up the keys for a given value requires looping through the whole dataset—O(n) time.
- Not cache-friendly. Many hash table implementations use linked lists, which don't put data next to each other in memory.

## Hash function
Hash function H(x) converts a key (x) into an index H(x).


**Open addressing**
Linear probing
Quadratic probing(fail attempt ^ 2)
Plus 3 rehash
Double hash
**Close addressing**

**objectives**
- Minimize collisions
- Uniform distribution of hash values
- Easy to calculate
- Resolve any collisions
  

## Sets
A set is like a hash map except it only stores keys, without values.