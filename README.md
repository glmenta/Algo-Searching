### Search => Types:

Linear, Binary, DFS, BFS

### Linear Search
```
=> Sequential => find target val inside a list;

=> similar to looping thru an array to find matching val;

Examples:
.indexOf();
.findIndex(fxn(){})
.find(fxn(){})
.includes();

Worst case: O(n)
Best case: O(1)
```

### Binary Search
```
=> is there a better way to find a num in a sorted list?

Ex: [1,4,6,9,12,34,45]

=> Instead of going iterating one at a time; we can sort first (in this case its already sorted)
    => then check if that middle val is lower/higher than our target
    => go left/right depending on above
    => now we change the efficiency of our search; from O(n) to O(logN)
    => we basically made a binary search tree;

=> Storing data in a data structure like a tree is more efficient than linear data structure like an array;
    => "DIVIDE AND CONQUER"
```

### Breadth First Search
```
=> Checks one level at a time from left to right;
```

### Depth First Search
```
=> Checks left most side until no children exist, go back up then go right then left, repeat.
=> Less memory than BFS
=> Walking through a maze; keep going as far as you can, if you are stuck, go back and find a different route
```

### BFS VS DFS
```
=> Both are O(n)
=> BFS:
    => Pros: shortest path, closer node;
    => Con: More memory used
=> DFS:
    => Pros: Less memory, does path exist?
    => Con: can be slow
=> if we know the location of node and its closer to root, best to use BFS
=> DFS is good if we dont know the location yet (check if it exists)
```

### When to use BFS VS DFS
```
=> If we known solution is close to root: BFS

=> If tree is very deep and solution is rare: BFS (DFS will take too long)

=> If tree is wide: DFS (BFS will use too much memory)

=> if solution is frequent but deep in tree: DFS

=> Determine whether a path exists between two nodes: DFS

=> Finding shortest path: BFS
```

### breathFirstSearch()
```
=> From top, then left to right for that level then next level repeat;
=> Keep a reference using a queue;

fxn BFS() {
    let curr = this.root;
    let list = [];
    let queue = [];

    queue.push(curr) {

    }

    while (queue.length > 0) {
        curr = queue.shift();
        list.push(curr.val)
        if (curr.left) {
            queue.push(curr.left)
        }
        if (curr.right) {
            queue.push(curr.right)
        }
    }
    return list;
}

fxn bfsRecursive(queue,list) {
    if (!queue.length) return list;
    let curr = this.queue.shift();
    list.push(curr.val)
        if (curr.left) {
            queue.push(curr.left)
        }
        if (curr.right) {
            queue.push(curr.right)
        }
    return bfsRecursive(queue,list)
}
```

### dfs()
```
=> 3 ways to implement dfs:
    => in-order, pre-order, post-order
        => PreOrder is useful for recreating the tree;

=> Most of the time, its better to use recursion for this!

fxn dfsInOrder() {
    return traverseInOrder()
}

fxn dfsPreOrder() {
    return traversePreOrder()
}

fxn dfsPostOrder() {
    return traversePostOrder()
}

fxn traverseInOrder(node, list) {
    if (node.left) {
        traverseInOrder(node.left, list)
    }
    list.push(node.val)
    if (node.right) {
        traverseInOrder(node.right, list)
    }
    return list;
}

fxn traversePreOrder(node, list) {
    list.push(node.val)
    if (node.left) {
        traverseInOrder(node.left, list)
    }
    if (node.right) {
        traverseInOrder(node.right, list)
    }
    return list;
}

fxn traversePostOrder(node, list) {
    if (node.left) {
        traverseInOrder(node.left, list)
    }
    if (node.right) {
        traverseInOrder(node.right, list)
    }
    list.push(node.val)
    return list;
}

Note:
=> The return statements in JavaScript functions inherently handle the process of "going back up" the recursive call stack.
=> When the function calls itself to traverse the left or right subtree, it doesn't immediately forget about the current execution context.
=> Instead, each recursive call creates a new instance of the function with its own set of local variables and parameters.
=> These instances are stacked on top of each other in what's known as the "call stack."
```
### Graph Traversals
```
```

### BFS and DFS in Graphs
```
=>BFS
    => Recommendations
        => Convert graph into a tree; we know information such as children
        => Helps us find shortest path/know which node is a neighbor

=> DFS
    => Maze solving; find deepest and backtrack until we find best route/exit;
    => Does path exist?

=> BFS assumes that each jump/path from 1 node to another is the same "weight" for that edge
    => distance between two nodes

=> Bellman and Dijkstra => best for shortest path problem
```
