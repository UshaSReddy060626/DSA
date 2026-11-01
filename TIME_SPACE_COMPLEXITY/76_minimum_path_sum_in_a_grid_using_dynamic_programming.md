## Question

Find the time and space complexities of this algorithm.

```python
def min_path_sum(grid):
    rows = len(grid)
    cols = len(grid[0])

    dp = [[0] * cols for _ in range(rows)]

    dp[0][0] = grid[0][0]

    for i in range(1, rows):
        dp[i][0] = dp[i - 1][0] + grid[i][0]

    for j in range(1, cols):
        dp[0][j] = dp[0][j - 1] + grid[0][j]

    for i in range(1, rows):
        for j in range(1, cols):
            dp[i][j] = grid[i][j] + min(
                dp[i - 1][j],
                dp[i][j - 1]
            )

    return dp[rows - 1][cols - 1]
```

Let:
- `r` = number of rows.
- `c` = number of columns.

Assume the grid is non-empty and the only allowed movements are right and down.

## Answer

- **Time Complexity:** \(O(rc)\)
- **Auxiliary Space:** \(O(rc)\)

## Explanation

### Step 1: Understand the DP table

```python
dp = [[0] * cols for _ in range(rows)]
```

The algorithm creates a table with `r` rows and `c` columns.

The number of cells is:

\[
r\times c
\]

Therefore, space complexity is:

\[
O(rc)
\]

### Step 2: Initialize the first column

```python
for i in range(1, rows):
```

This loop runs approximately `r` times.

Its complexity is:

\[
O(r)
\]

### Step 3: Initialize the first row

```python
for j in range(1, cols):
```

This loop runs approximately `c` times.

Its complexity is:

\[
O(c)
\]

### Step 4: Fill the remaining cells

```python
for i in range(1, rows):
    for j in range(1, cols):
```

The nested loops process approximately every remaining cell once.

Their complexity is:

\[
O(rc)
\]

### Step 5: Calculate total time

\[
T(r,c)=O(r)+O(c)+O(rc)
\]

The dominant term is:

\[
\boxed{O(rc)}
\]

## Key Takeaway

For grid-based dynamic programming:

- Every cell processed once: \(O(rc)\).
- A table containing every cell: \(O(rc)\) space.

If the grid is square with `n` rows and `n` columns, both complexities become \(O(n^2)\).