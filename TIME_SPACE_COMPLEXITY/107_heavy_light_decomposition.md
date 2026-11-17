## Question

Given a tree with \(n\) vertices, implement Heavy-Light Decomposition to support path queries and point updates.

Determine the time and space complexity.

**Answer:**

- Construction: \(O(n)\)
- Path Query: \(O(\log^2 n)\) with a segment tree.
- Point Update: \(O(\log n)\)
- Space Complexity: \(O(n)\)

## Explanation

Heavy-Light Decomposition is a technique that divides a tree into smaller chains to make path queries efficient.

**Step 1: Calculate subtree sizes**

Find the number of nodes in every node's subtree using DFS.

This takes:

\[
O(n)
\]

**Step 2: Divide the tree into chains**

Choose the child with the largest subtree as the heavy child.

Other child edges are considered light edges.

This divides the tree into heavy chains.

**Step 3: Perform path queries**

A path between two nodes can be divided into several heavy-chain segments.

There are at most \(O(\log n)\) such segments.

A segment tree answers each segment query in \(O(\log n)\).

Therefore:

\[
O(\log n)\times O(\log n)
\]

\[
=O(\log^2 n)
\]

**Step 4: Calculate update complexity**

A point update changes one position in the segment tree.

Therefore:

\[
O(\log n)
\]

**Step 5: Calculate space complexity**

The decomposition arrays and segment tree require linear space.

\[
S(n)=O(n)
\]

### Key Takeaway

Heavy-Light Decomposition makes tree path queries efficient.

- Construction: \(O(n)\)
- Path query: \(O(\log^2 n)\)
- Point update: \(O(\log n)\)
- Space: \(O(n)\)