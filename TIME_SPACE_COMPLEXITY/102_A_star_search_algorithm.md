## Question

Given a weighted graph with \(V\) vertices and \(E\) edges, find the shortest path between a starting vertex and a destination using the A* Search Algorithm.

Determine its time and space complexity.

**Answer:**

For a standard implementation using a priority queue:

- Worst-case Time Complexity: Exponential in the search depth in general search-tree analysis.
- Space Complexity: Exponential in the search depth in general search-tree analysis.

For a finite graph implementation, the exact complexity depends on the heuristic, graph representation, and whether improved paths cause nodes to be re-expanded. A common practical bound for an implementation that processes each vertex once is \(O((V+E)\log V)\), but that bound does not apply to every A* implementation.

### Explanation

A* is a pathfinding algorithm that uses both the distance already travelled and an estimate of the remaining distance.

**Step 1: Calculate the evaluation function**

A* uses:

\[
f(n)=g(n)+h(n)
\]

Where:

- \(g(n)\) = actual cost from the starting point to node \(n\).
- \(h(n)\) = estimated cost from node \(n\) to the destination.
- \(f(n)\) = estimated total path cost.

**Step 2: Use a priority queue**

The algorithm selects the node with the smallest \(f(n)\) value.

**Step 3: Explore neighbouring nodes**

Calculate the new path cost for each neighbour.

If a better path is found, update its cost and priority.

**Step 4: Reach the destination**

Continue until the destination is selected for processing.

With an admissible heuristic, A* can find an optimal path under the usual graph-search assumptions.

**Step 5: Understand complexity**

Unlike algorithms with a simple fixed polynomial bound, A* can explore exponentially many states in the worst case.

Its performance depends heavily on the quality of the heuristic.

### Key Takeaway

A* combines actual path cost and estimated remaining cost.

\[
f(n)=g(n)+h(n)
\]

- Uses a priority queue.
- Can find optimal paths with a suitable heuristic.
- Worst-case search effort can be exponential.