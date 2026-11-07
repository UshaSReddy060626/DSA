## Question

Consider a Disjoint Set Union (DSU) data structure containing \(n\) elements.

It supports two operations:

1. `find(x)` – finds the group to which element x belongs.
2. `union(a, b)` – combines the groups containing a and b.

Using path compression and union by size, determine the time and space complexity for \(m\) operations.

**Answer:**

- Initialization: \(O(n)\)
- Each operation: \(O(\alpha(n))\) amortized.
- Total for \(m\) operations: \(O(n+m\alpha(n))\).
- Space complexity: \(O(n)\).

## Explanation

**Step 1: Initialization**

Initially, every element belongs to its own group.

For example:

`1   2   3   4   5`

Each element is its own parent.

Creating the parent and size arrays takes \(O(n)\) time and space.

**Step 2: Find operation**

The `find(x)` operation identifies the representative (root) of the group.

Path compression makes future searches faster by directly connecting visited elements to the root.

**Step 3: Union operation**

The `union(a, b)` operation combines two groups.

Union by size attaches the smaller group to the larger group, helping keep the tree shallow.

**Step 4: Total complexity**

With both optimizations, each operation takes nearly constant amortized time:

\[
O(\alpha(n))
\]

Here, \(\alpha(n)\) is the inverse Ackermann function. It grows so slowly that for practical input sizes, it is effectively a very small constant.

For \(m\) operations:

\[
T(n,m)=O(n+m\alpha(n))
\]

### Key Takeaway

DSU efficiently manages groups or connected components.

- Initialization: \(O(n)\)
- Operations: \(O(\alpha(n))\) amortized each.
- Total: \(O(n+m\alpha(n))\)
- Space: \(O(n)\)