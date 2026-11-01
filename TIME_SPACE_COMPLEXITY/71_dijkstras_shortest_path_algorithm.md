## Question

Find the time complexity of Dijkstra's algorithm when implemented using an adjacency list and a min-heap.

```python
import heapq

def dijkstra(graph, start):
    distances = {node: float("inf") for node in graph}
    distances[start] = 0

    heap = [(0, start)]

    while heap:
        distance, node = heapq.heappop(heap)

        if distance > distances[node]:
            continue

        for neighbor, weight in graph[node]:
            new_distance = distance + weight

            if new_distance < distances[neighbor]:
                distances[neighbor] = new_distance
                heapq.heappush(heap, (new_distance, neighbor))

    return distances
```

Assume the graph has `V` vertices and `E` edges, and all edge weights are non-negative.

## Answer

**Time Complexity: \(O((V+E)\log V)\)** as a standard bound for this lazy-heap implementation.

## Explanation

### Step 1: Initialize distances

```python
distances = {node: float("inf") for node in graph}
```

The algorithm initializes a distance for every vertex.

This takes:

\[
O(V)
\]

### Step 2: Process the min-heap

```python
distance, node = heapq.heappop(heap)
```

Removing an element from a heap takes logarithmic time in the heap size.

### Step 3: Explore neighboring vertices

```python
for neighbor, weight in graph[node]:
```

Across the graph, adjacency lists contain `O(E)` edge entries.

A successful relaxation can insert an entry into the heap. There can be up to `O(E)` such insertions in this implementation.

Heap operations therefore contribute a logarithmic factor, giving the standard bound:

\[
O((V+E)\log V)
\]

## Key Takeaway

Dijkstra's algorithm finds shortest paths from one source when edge weights are non-negative.

Remember:

- BFS for unweighted shortest paths: \(O(V+E)\).
- Dijkstra with a binary heap: commonly \(O((V+E)\log V)\).

