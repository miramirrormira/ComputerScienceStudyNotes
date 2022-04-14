# Trees

## Binary Tree
**A binary tree is a tree where every node has two or fewer children. The children are usually called left and right.**

```
  class BinaryTreeNode(object):

    def __init__(self, value):
        self.value = value
        self.left  = None
        self.right = None
```

## Binary Tree Types
### perfect tree
A Binary tree is a Perfect Binary Tree in which all the internal nodes have two children and all leaf nodes are at the same level. 

**properties of perfect tree**
1. the number of total nodes on each "level" doubles as we move down the tree
2. the number of nodes on the last level is equal to the sum of the number of nodes on all other levels plus 1. In other words, about half of our nodes are on the last level

n: number of nodes
h: number of levels of the tree

n = 2^0 + 2^1 + 2^2 + ... + 2^(h-1) = 2^h - 1
h = log(n+1), base is 2


### Binary Search Tree
A binary search tree is a binary tree in which every node fits a specific ordering property: all left descendents <= n < all right descendents. This must be true for each node n.
[GeeksforGeeks](https://www.geeksforgeeks.org/binary-search-tree-data-structure/?ref=gcse)
- The left subtree of a node contains only nodes with keys lesser than the node’s key.
- The right subtree of a node contains only nodes with keys greater than the node’s key.
- The left and right subtree each must also be a binary search tree.

### Balanced vs. Unbalanced
[How to determine if a binary tree is height-balanced](https://www.geeksforgeeks.org/how-to-determine-if-a-binary-tree-is-balanced/)
Height-balanced tree: a tree where no leaf is farther away from the root than any other leaf.

**Height-balancing schemes**
An empty tree is height-balanced. A non-empty binary tree T is balanced if: 
- Left subtree of T is balanced 
- Right subtree of T is balanced 
- The difference between heights of left subtree and right subtree is not more than 1.
 
### Full Binary Trees
A Binary Tree is a full binary tree if every node has 0 or 2 children. We can also say a full binary tree is a binary tree in which all nodes except leaf nodes have two children. 
```
               18
           /       \  
         15         30  
        /  \        /  \
      40    50    100   40

             18
           /    \   
         15     20    
        /  \       
      40    50   
    /   \
   30   50

               18
            /     \  
          40       30  
                   /  \
                 100   40
```

### Complete Binary Trees
A Binary Tree is a Complete Binary Tree if all the levels are completely filled except possibly the last level and the last level has all keys as left as possible 

The following are examples of Complete Binary Trees 
```
               18
           /       \  
         15         30  
        /  \        /  \
      40    50    100   40


               18
           /       \  
         15         30  
        /  \        /  \
      40    50    100   40
     /  \   /
    8   7  9 
```

### Binary heap
[source](https://www.geeksforgeeks.org/binary-heap/?ref=gcse)
A Binary Heap is a Binary Tree with following properties.
- It’s a complete tree (All levels are completely filled except possibly the last level and the last level has all keys as left as possible). This property of Binary Heap makes them suitable to be stored in an array.

- A Binary Heap is either Min Heap or Max Heap. In a Min Binary Heap, the key at root must be minimum among all keys present in Binary Heap. The same property must be recursively true for all nodes in Binary Tree. Max Binary Heap is similar to MinHeap.

example:
```
            10                      10
         /      \               /       \  
       20        100          15         30  
      /                      /  \        /  \
    30                     40    50    100   40
```

### Tries (Prefix Trees)
Cracking the coding interviews, Chapter 4, page 105

## Binary Tree Traversal
1. In-Order
   visit the left branch, then the current node, finally the right branch
2. Pre-Order
   visit the current node, then the child node
3. Post-Order
   visit the children, then the current node


