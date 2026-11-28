## Question

Find the time and auxiliary space complexity of the following algorithm.

Binary Lifting preprocesses a tree so that it can efficiently find the Lowest Common Ancestor of two nodes.

```python
def preprocess(tree, root, n):
    LOG = n.bit_length()

    up = [[-1] * LOG for _ in range(n)]
    depth = [0] * n

    def dfs(node, parent):
        up[node][0] = parent

        for j in range(1, LOG):
            if up[node][j - 1] != -1:
                up[node][j] = up[up[node][j - 1]][j - 1]

        for child in tree[node]:
            if child != parent:
                depth[child] = depth[node] + 1
                dfs(child, node)

    dfs(root, -1)
    return up, depth


def lca(a, b, up, depth):
    LOG = len(up[0])

    if depth[a] < depth[b]:
        a, b = b, a

    diff = depth[a] - depth[b]

    for j in range(LOG):
        if diff & (1 << j):
            a = up[a][j]

    if a == b:
        return a

    for j in range(LOG - 1, -1, -1):
        if up[a][j] != up[b][j]:
            a = up[a][j]
            b = up[b][j]

    return up[a][0]
```

Let:
- \(n\) = number of nodes in the tree
- \(q\) = number of LCA queries

Assume the input is a connected tree and the DFS is implemented with sufficient recursion-stack capacity.

## Answer

- **Preprocessing Time:** \(O(n\log n)\)
- **One LCA Query:** \(O(\log n)\)
- **Total Time for \(q\) Queries:** \(O(n\log n+q\log n)\)
- **Auxiliary Space:** \(O(n\log n)\)

## Explanation

### Step 1: Create the ancestor table

```python
up = [[-1] * LOG for _ in range(n)]
```

Each of the \(n\) nodes stores up to \(\log n\) ancestors.

Therefore:

\[
O(n\log n)
\]

### Step 2: Understand DFS preprocessing

```python
dfs(root, -1)
```

DFS visits every node once.

For every node, the algorithm calculates its ancestors at different powers of two.

The inner loop runs \(O(\log n)\) times per node.

Therefore:

\[
O(n)\times O(\log n)
\]

\[
=O(n\log n)
\]

### Step 3: Understand the first query loop

```python
for j in range(LOG):
```

This loop checks the binary representation of the depth difference.

It lifts the deeper node upward until both nodes are at the same depth.

There are \(O(\log n)\) iterations.

Time:

\[
O(\log n)
\]

### Step 4: Understand the second query loop

```python
for j in range(LOG - 1, -1, -1):
```

This loop moves both nodes upward using powers of two until their parents are the same.

Again, it performs \(O(\log n)\) iterations.

Time:

\[
O(\log n)
\]

### Step 5: Calculate one query

Both loops take \(O(\log n)\).

Therefore:

\[
\boxed{O(\log n)}
\]

### Step 6: Calculate total time

Preprocessing:

\[
O(n\log n)
\]

For \(q\) queries:

\[
O(q\log n)
\]

Total:

\[
\boxed{O(n\log n+q\log n)}
\]

### Step 7: Calculate space

- Ancestor table: \(O(n\log n)\)
- Depth array: \(O(n)\)
- DFS recursion stack: \(O(n)\) in the worst case for a tree shaped like a chain.

Therefore:

\[
\boxed{O(n\log n)}
\]

## Key Takeaway

Binary Lifting is an example of trading extra preprocessing and memory for faster queries.

- Preprocessing: \(O(n\log n)\)
- One LCA query: \(O(\log n)\)
- Multiple queries: \(O(q\log n)\)
- Auxiliary space: \(O(n\log n)\)

It is especially useful when a tree receives many ancestor or LCA queries.