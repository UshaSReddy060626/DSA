## Question

Given a connected, weighted, undirected graph with \(V\) vertices and \(E\) edges, find its Minimum Spanning Tree (MST) using Kruskal's Algorithm.

Determine the time and space complexity.

**Answer:**

- Time Complexity: \(O(E\log E)\)
- Auxiliary Space Complexity: \(O(V)\), excluding the input edge list and sorting storage.

### Explanation

A Minimum Spanning Tree connects all vertices with the minimum possible total edge weight without creating a cycle.

**Step 1: Sort all edges**

Sort the graph edges in increasing order of their weights.

For example:

| Edge | Weight |
|---|---:|
| A–B | 2 |
| B–C | 3 |
| A–C | 5 |
| C–D | 6 |

Sorting \(E\) edges takes:

\[
O(E\log E)
\]

**Step 2: Select the smallest edge**

Choose the edge with the smallest weight.

Add it to the MST if it does not create a cycle.

**Step 3: Detect cycles**

Use the Disjoint Set Union (DSU) data structure.

- If two vertices belong to different sets, add the edge.
- If they already belong to the same set, skip the edge.

**Step 4: Continue selecting edges**

Repeat until the MST contains \(V-1\) edges.

**Step 5: Calculate complexity**

- Sorting edges: \(O(E\log E)\)
- DSU operations: \(O(E\alpha(V))\) amortized.

Sorting dominates the overall complexity.

Therefore:

\[
\boxed{O(E\log E)}
\]

The DSU parent and size arrays require:

\[
\boxed{O(V)}
\]

auxiliary space.

### Key Takeaway

Kruskal's Algorithm builds a Minimum Spanning Tree by selecting the smallest edges without creating cycles.

- Time: \(O(E\log E)\)
- Auxiliary space: \(O(V)\), excluding input and sorting storage.