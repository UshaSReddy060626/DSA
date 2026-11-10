## Question

Given a weighted graph with \(V\) vertices, find the shortest distances between every pair of vertices using the Floyd-Warshall algorithm.

Determine its time and space complexity.

**Answer:**

- Time Complexity: \(O(V^3)\)
- Space Complexity: \(O(V^2)\)

### Explanation

Floyd-Warshall finds the shortest path between every possible pair of vertices in a graph.

**Step 1: Create a distance matrix**

Create a \(V \times V\) matrix.

Each cell stores the distance between two vertices.

**Step 2: Consider intermediate vertices**

For every vertex \(k\), check whether travelling from vertex \(i\) to vertex \(j\) through \(k\) gives a shorter path.

The update rule is:

\[
dist[i][j] = \min(dist[i][j],\ dist[i][k]+dist[k][j])
\]

**Step 3: Use three nested loops**

The algorithm uses:

- First loop: selects an intermediate vertex.
- Second loop: selects the starting vertex.
- Third loop: selects the destination vertex.

Each loop runs \(V\) times.

Therefore:

\[
T(V)=V\times V\times V
\]

\[
\boxed{O(V^3)}
\]

**Step 4: Calculate space complexity**

The distance matrix contains \(V \times V\) entries.

Therefore:

\[
\boxed{O(V^2)}
\]

### Key Takeaway

Floyd-Warshall calculates shortest paths between all pairs of vertices.

- Time: \(O(V^3)\)
- Space: \(O(V^2)\)

It supports negative edge weights but not negative-weight cycles.