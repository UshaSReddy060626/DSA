## Question

Given a weighted directed graph with \(V\) vertices and \(E\) edges, find the shortest distance from a source vertex to all other vertices using the Bellman-Ford algorithm.

Determine the time and space complexity.

**Answer:**

- Time Complexity: \(O(VE)\)
- Auxiliary Space Complexity: \(O(V)\)

### Explanation

Bellman-Ford finds the shortest paths from one source vertex to all other vertices. It can also handle negative edge weights.

**Step 1: Initialize distances**

Create a distance array of size \(V\).

- Set the source distance to 0.
- Set all other distances to infinity.

**Step 2: Relax all edges**

Relaxation means checking whether a shorter path can be found through an edge.

For every edge \((u,v)\) with weight \(w\):

\[
dist[v]=\min(dist[v],dist[u]+w)
\]

Repeat this process \(V-1\) times.

**Step 3: Check for negative cycles**

Perform one additional pass over all edges.

If any distance can still be reduced, the graph contains a reachable negative-weight cycle.

**Step 4: Calculate time complexity**

- Number of iterations: \(V-1\)
- Edges checked in each iteration: \(E\)

Therefore:

\[
T(V,E)=O(V\times E)
\]

\[
\boxed{O(VE)}
\]

**Step 5: Calculate space complexity**

The distance array stores \(V\) values.

Therefore:

\[
\boxed{O(V)}
\]

### Key Takeaway

Bellman-Ford calculates shortest paths from a single source and supports negative edge weights.

- Time: \(O(VE)\)
- Auxiliary space: \(O(V)\)
- Can detect reachable negative-weight cycles.