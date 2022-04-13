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

### perfect tree
**A perfect tree is a tree of which every level is completely full.**

**properties of perfect tree**
1. the number of total nodes on each "level" doubles as we move down the tree
2. the number of nodes on the last level is equal to the sum of the number of nodes on all other levels plus 1. In other words, about half of our nodes are on the last level

n: number of nodes
h: number of levels of the tree

n = 2^0 + 2^1 + 2^2 + ... + 2^(h-1) = 2^h - 1
h = log(n+1), base is 2