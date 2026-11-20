## Question

Find the time and auxiliary space complexity.

```python
def dfs(graph, node, visited):
    if node in visited:
        return

    visited.add(node)

    for neighbor in graph[node]:
        dfs(graph, neighbor, visited)
```

Assume the graph is represented using an adjacency list and DFS starts from one vertex.

Let:
- \(V\) = number of vertices.
- \(E\) = number of edges.

## Answer

- **Time Complexity:** \(O(V+E)\) average
- **Auxiliary Space Complexity:** \(O(V)\)

## Detailed Explanation

**Step 1: Understand DFS**

Depth First Search explores a graph by visiting a vertex and then recursively exploring its unvisited neighbors.

**Step 2: Analyze vertex visits**

The `visited` set ensures each vertex is processed only once.

Therefore, vertex processing takes:

\[
O(V)
\]

**Step 3: Analyze edge visits**

DFS examines the neighbors in each vertex's adjacency list.

Across the entire traversal, the total number of adjacency entries examined is:

\[
O(E)
\]

For an undirected graph, each edge appears twice in the adjacency lists, but this is still \(O(E)\).

**Step 4: Calculate total time**

\[
O(V)+O(E)
\]

\[
\boxed{O(V+E)}
\]

**Step 5: Calculate auxiliary space**

The `visited` set can store up to \(V\) vertices.

The recursion stack can also reach \(O(V)\) depth in the worst case.

Therefore:

\[
\boxed{O(V)}
\]

## Key Takeaway

DFS complexity depends on both vertices and edges. For adjacency-list representation, remember \(O(V+E)\), not simply \(O(V^2)\).