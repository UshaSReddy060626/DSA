## Question

Given a directed acyclic graph (DAG) with \(V\) vertices and \(E\) edges, find the time and space complexity of topological sorting using Kahn's Algorithm.

**Answer:**

- Time Complexity: \(O(V+E)\)
- Space Complexity: \(O(V)\)

## Explanation

Topological sorting arranges vertices in an order where every vertex appears before the vertices that depend on it.

**Step 1: Calculate in-degree**

In-degree means the number of incoming edges to a vertex.

We visit all vertices and edges to calculate their in-degrees.

Time: \(O(V+E)\).

**Step 2: Add vertices to a queue**

Add all vertices with in-degree zero to a queue.

At most \(V\) vertices are added.

**Step 3: Process the queue**

- Remove one vertex from the queue.
- Add it to the result.
- Visit its neighbouring vertices.
- Reduce their in-degrees.
- If a neighbour's in-degree becomes zero, add it to the queue.

Each vertex is processed once, and each edge is visited once.

**Step 4: Calculate complexity**

\[
T(V,E)=O(V)+O(E)
\]

\[
\boxed{O(V+E)}
\]

The queue, in-degree array, and result array require \(O(V)\) space, excluding the input graph.

### Key Takeaway

Topological sorting using Kahn's Algorithm takes:

- Time: \(O(V+E)\)
- Auxiliary space: \(O(V)\)

It is commonly used in task scheduling and dependency management.