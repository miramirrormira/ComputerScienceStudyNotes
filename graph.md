# Graph

## Definition
**A graph organizes items in an interconnected network**
Each item is a **node** (**vertex**). Nodes are connected by **edges**.

## Features
### Directed or undirected
In **directed** graphs, edges point from the node at one end to the node at the other end. In **undirected** graphs, the edges simply connect the nodes at each end.

### Cyclic or acyclic
A graph is **cyclic** if it has a cycle—an unbroken series of nodes with no repeating nodes or edges that connects back to itself. Graphs without cycles are **acyclic**.


### Weighted or unweighted
If a graph is **weighted**, each edge has a "weight." The weight could, for example, represent the distance between two locations, or the cost or time it takes to travel between the locations.

### Legal coloring
A **graph coloring** is when you assign colors to each node in a graph. A **legal coloring** means no adjacent nodes have the same color:


## Representations
```
1 --- 0
|\
| \
|  \
3 -- 2
```

### Edge list
```
  graph = [[0, 1], [1, 2], [1, 3], [2, 3]]
```
[0, 1] represents the edge between node 0 and node 1

### Adjacency list
A list where the index represents the node and the value at that index is a list of the node's neighbors:
```
graph = [
    [1],
    [0, 2, 3],
    [1, 3],
    [1, 2],
]
```
[0, 2, 3] at index 1 means node 1 is connected to node 0, node 2, and node 3

We could also use a dictionary where the keys represent the node and the values are the lists of neighbors. This would be useful if the nodes were represented by strings, objects, or otherwise didn't map cleanly to list indices.
```
graph = {
    0: [1],
    1: [0, 2, 3],
    2: [1, 3],
    3: [1, 2],
}
```

### Adjacency matrix
A matrix of 0s and 1s indicating whether node x connects to node y (0 means no, 1 means yes).
```
graph = [
    [0, 1, 0, 0],
    [1, 0, 1, 1],
    [0, 1, 0, 1],
    [0, 1, 1, 0],
]
```
[0, 1, 0, 0] at index 0 means node 0 is connected to node 1, not other nodes
[0, 1, 1, 0] at index 3 means node 3 is connected to node 1 and node 2, but not node 0 and node 3


## Algorithms
### BFS: Breadth-first search
Breadth-first search (BFS) is a method for exploring a tree or graph. In a BFS, you first explore all the nodes one step away, then all the nodes two steps away, etc.

**implement BFS**
Pseudocode using **recursion**
```
void search(Node root):
    if (root == null) return
    visit(root)
    root.visited = true
    for each Node n in root.adjacent:
        if n.visited == false:
            search(n)
```

**Advantages**
A BFS will find the shortest path between the starting point and any other reachable node. A depth-first search will not necessarily find the shortest path.

**Disadvantages**
A BFS on a binary tree generally requires more memory than a DFS.

### DFS: Depth-first search
In a DFS, you go as deep as possible down one path before backing up and trying a different one. Depth-first search is like walking through a corn maze. You explore one path, hit a dead end, and go back and try a different one.

**implement BFS**
Pseudocode using **queue**
```
void search(Node root):
    Queue queue = new Queue()
    root.marked = true
    queue.enqueue(root)

    while !queue.isEmpty():
        Node r = queue.dequeue()
        visit(r)
        for each Node n in r.adjacent:
            if n.marked == false:
                n.marked = true
                queue.enqueue(n)
```

**Advantages**
Depth-first search on a binary tree generally requires less memory than breadth-first.
Depth-first search can be easily implemented with recursion.

**Disadvantages**
A DFS doesn't necessarily find the shortest path to a node, while breadth-first search does.

### Bidirectional Search
Bidirectional search is a graph search algorithm which find smallest path from source to goal vertex. It runs two simultaneous search
1. Forward search from source/initial vertex toward goal vertex
2. Backward search from goal/target vertex toward source vertex

**bidirectional search is faster**
Suppose if branching factor of tree is b and distance of goal vertex from source is d, then the normal BFS/DFS searching complexity would be O(bd). On the other hand, if we execute two search operation then the complexity would be O(bd/2) for each search and total complexity would be O(bd/2 +bd/2) which is far less than O(bd).

**When to use bidirectional approach?**
We can consider bidirectional approach when- 
- Both initial and goal states are unique and completely defined.
- The branching factor is exactly the same in both directions.

### Graph problems
1. **Is there a path** between two nodes in this undirected graph? Run DFS or BFS from one node and see if you reach the other one.

2. What's the **shortest path** between two nodes in this undirected, unweighted graph? Run BFS from one node and backtrack once you reach the second. Note: *BFS always finds the shortest path, assuming the graph is undirected and unweighted. DFS does not always find the shortest path.*

3. Can this undirected graph be **colored** with two colors? Run BFS, assigning colors as nodes are visited. Abort if we ever try to assign a node a color different from the one it was assigned earlier.

4. Does this undirected graph **have a cycle**? Run BFS, keeping track of the number of times we're visiting each node. If we ever visit a node twice, then we have a cycle.

### Advanced graph algorithms
1. Dijkstra's Algorithm: Finds the shortest path from one node to all other nodes in a weighted graph.
2. Topological Sort: Arranges the nodes in a directed, acyclic graph in a special order based on incoming edges.
3. Minimum Spanning Tree: Finds the cheapest set of edges needed to reach all nodes in a weighted graph.