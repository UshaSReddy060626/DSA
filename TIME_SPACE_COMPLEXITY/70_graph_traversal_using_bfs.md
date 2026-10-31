## Question

Find the time and space complexities of this Breadth-First Search (BFS) implementation.

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])

    visited.add(start)

    while queue:
        node = queue.popleft()

        for neighbor in graph[node]:
            if neighbor not in visited:
                visited.add(neighbor)
                queue.append(neighbor)
```

Assume the graph has `V` vertices and `E` edges, and is represented using an adjacency list.

## Answer

- **Time Complexity:** \(O(V+E)\)
- **Auxiliary Space:** \(O(V)\)

## Explanation

### Step 1: Understand BFS

BFS visits graph nodes level by level using a queue.

It starts from one node, visits its neighbors, and then explores the next level.

### Step 2: Analyze the queue operations

Each vertex is added to the queue at most once because the `visited` set prevents repeated visits.

Queue insertion and removal take \(O(1)\) time per operation.

Total vertex-processing work:

\[
O(V)
\]

### Step 3: Analyze the neighbor traversal

The algorithm examines the adjacency list of each visited vertex.

Across the entire graph, the total number of adjacency-list entries is \(O(E)\) for a directed graph and also \(O(E)\) for an undirected graph when counting both directions.

Therefore, edge-processing work is:

\[
O(E)
\]

### Step 4: Combine the work

\[
T(V,E)=O(V)+O(E)
\]

\[
\boxed{O(V+E)}
\]

The visited set and queue can each hold up to `V` vertices.

\[
\boxed{O(V)\text{ auxiliary space}}
\]

## Key Takeaway

For graph traversal using an adjacency list:

- BFS: \(O(V+E)\)
- DFS: \(O(V+E)\)

Remember that graph complexity depends on both vertices and edges, not just the number of vertices.