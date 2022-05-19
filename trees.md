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

$$
n = 2^0 + 2^1 + 2^2 + ... + 2^{h-1} = 2^h - 1
$$
$$
h = log_{2}(n+1)
$$

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
           /    \  
         15      30  
        /  \    /  \
      40    50 100 40

             18
           /    \   
         15     20    
        /  \       
      40    50   
    /   \
   30   50

              18
            /    \  
          40      30  
                 /  \
                100 40
```

### Complete Binary Trees
A Binary Tree is a Complete Binary Tree if all the levels are completely filled except possibly the last level and the last level has all keys as left as possible 

The following are examples of Complete Binary Trees 
```
             18
           /    \  
         15      30  
        /  \    /  \
      40   50  100  40


             18
           /    \  
         15      30  
        /  \    /  \
      40    50 100  40
     /  \   /
    8   7  9 
```

### Binary heap
A [Binary Heap](https://www.geeksforgeeks.org/binary-heap/?ref=gcse) is a Binary Tree with following properties.
- It’s a complete tree (All levels are completely filled except possibly the last level and the last level has all keys as left as possible). This property of Binary Heap makes them suitable to be stored in an array.

- A Binary Heap is either Min Heap or Max Heap. In a Min Binary Heap, the key at root must be minimum among all keys present in Binary Heap. The same property must be recursively true for all nodes in Binary Tree. Max Binary Heap is similar to MinHeap.

example:
```
           10                   10
         /    \               /    \  
       20     100           15      30  
      /                    /  \    /  \
    30                   40   50  100  40
```

### Tries (Prefix Trees)
Cracking the coding interviews, Chapter 4, page 105

## Binary Tree Traversal

### Depth First Search

Two Approaches:
1. Recursive
   - simple
2. Iterative
   - faster
   - doesn't have call stack limitations (python has a max call stack limitation of 1000)
  
Three DFS traversing methods:
1. In-Order
   visit the left branch, then the current node, finally the right branch.

   [Iterative Inorder Traversal](https://www.geeksforgeeks.org/inorder-tree-traversal-without-recursion/?ref=gcse)

   **Uses:**
   In the case of binary search trees(BST), in-order traversal gives nodes in non-decreasing order. To get nodes of BST in non-increasing order, a variation of in-order traversal where in-order traversal reversed can be used.
   ```
             4
           /   \
          2     6
         / \   / \
        1   3 5   8
                 / \
                7   9
   ```

   ```
    def inorder_traversal_recursive(root):
        result = []
        if root:
            result = inorder_traversal_recursive(root.left)
            result.append(root.value)
            result = result + inorder_traversal_recursive(root.right)
        return result

    def printInorderIterative(root):
        current = root
        stack = deque()

        while True:
            if current:
                stack.append(current)
                current = current.left
            elif stack:
                current = stack.pop()
                print(current.value)
                current = current.right
            else:
                break

   ```

2. Pre-Order
   visit the current node, then the child node

   [Iterative Preorder Traversal](https://www.geeksforgeeks.org/iterative-preorder-traversal/?ref=gcse)

   **Uses:**
   - create a copy of the tree
   - get prefix expression on an expression tree
   ```
             1
           /   \
          2     5
         / \   / \
        3   4 6   7
                 / \
                8   9
   ```
   ```
    def preorder_traversal_recursive(root):
        result = []
        if root:
            result.append(root.value)
            result = result + preorder_traversal_recursive(root.left)
            result = result + preorder_traversal_recursive(root.right)
        return result
    
    def printPreorderIterative1(root):
        stack = deque([root])
        while stack:
            node = stack.pop()
            print(node.value)
            if node.right:
                stack.append(node.right)
            if node.left:
                stack.append(node.left)

    def print_preorder_iterative2(root):
        if root is None:
            return
        stack = deque()
        current = root
        while stack or current:
            while current:
                print(current.value)
                if current.right:
                    stack.append(current.right)
                current = current.left
            if stack:
                current = stack.pop()
   ```


3. Post-Order
   visit the children, then the current node

   **Uses:**
   - [delete the tree](https://www.geeksforgeeks.org/write-a-c-program-to-delete-a-tree/)
   - get the postfix expression of an expression tree

   [Interative Postorder Traversal](https://www.geeksforgeeks.org/iterative-postorder-traversal/)

   ```
             9
           /   \
          3     8
         / \   / \
        1   2 4   7
                 / \
                5   6
   ```
   ```
    def postorder_traversal_recursive(root):
        result = []
        if root:
            result = postorder_traversal_recursive(root.left)
            result = result + postorder_traversal_recursive(root.right)
            result.append(root.value)
        return result

    ## method 1: using 2 stacks
    def print_postorder_iterative1(root):
        if root is None:
            return
        stack1 = deque()
        stack2 = deque()
        stack1.append(root)
        while stack1:
            node = stack1.pop()
            stack2.append(node)
            if node.left:
                stack1.append(node.left)
            if node.right:
                stack1.append(node.right)
        while stack2:
            node = stack2.pop()
            print(node.value)

    ## method 2: using 1 stack
    def print_postorder_iterative2(root):
        if root is None:
            return
        stack = deque()
        current = root
        while True:
            while current:
                if current.right:
                    stack.append(current.right)
                stack.append(current)
                current = current.left
            current = stack.pop()
            if current.right and len(stack) > 0 and stack[-1] == current.right:
                stack.pop()
                stack.append(current)
                current = current.right
            else:
                print(current.value)
                current = None
            if len(stack) == 0:
                break

    ## method 3: using 1 stack
    def print_postorder_iterative3(root):
        stack = deque()
        while True:
            while root is not None:
                stack.append(root)
                stack.append(root)
                root = root.left
            if len(stack) == 0:
                return
            root = stack.pop()
            if len(stack) > 0 and stack[-1] == root:
                root = root.right
            else:
                print(root.value)
                root = None

    ## method 4: using 1 stack and 1 hashmap
    def print_postorder_iterative4(root):
        stack = deque()
        unordered_map = {}
        stack.append(root)
        counter = 0
        while stack and counter < 100:
            counter += 1
            unordered_map[stack[-1]] = 1
            if stack[-1].left and stack[-1].left not in unordered_map:
                stack.append(stack[-1].left)
                continue
            if stack[-1].right and stack[-1].right not in unordered_map:
                stack.append(stack[-1].right)
                continue
            print(stack[-1].value)
            stack.pop()
   ```