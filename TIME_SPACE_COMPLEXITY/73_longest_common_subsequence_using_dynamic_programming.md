## Question

Find the time and space complexities of this algorithm.

```python
def longest_common_subsequence(a, b):
    m = len(a)
    n = len(b)

    dp = [[0] * (n + 1) for _ in range(m + 1)]

    for i in range(1, m + 1):
        for j in range(1, n + 1):

            if a[i - 1] == b[j - 1]:
                dp[i][j] = 1 + dp[i - 1][j - 1]

            else:
                dp[i][j] = max(
                    dp[i - 1][j],
                    dp[i][j - 1]
                )

    return dp[m][n]
```

Let:
- `m` = length of string `a`.
- `n` = length of string `b`.

## Answer

- **Time Complexity:** \(O(mn)\)
- **Auxiliary Space:** \(O(mn)\)

## Explanation

### Step 1: Understand the DP table

The algorithm creates a two-dimensional table:

```python
dp = [[0] * (n + 1) for _ in range(m + 1)]
```

The table has `(m + 1)` rows and `(n + 1)` columns.

Therefore, it contains:

\[
(m+1)(n+1)
\]

cells, requiring \(O(mn)\) space.

### Step 2: Analyze the nested loops

The outer loop runs `m` times.

The inner loop runs `n` times for every outer iteration.

Total iterations:

\[
m\times n
\]

### Step 3: Analyze the operations inside

Each iteration performs:
- One character comparison.
- A constant number of array accesses.
- One assignment or maximum comparison.

Each iteration takes \(O(1)\) time.

### Step 4: Calculate total time

\[
T(m,n)=m\times n\times O(1)
\]

\[
\boxed{O(mn)}
\]

## Key Takeaway

Two-dimensional dynamic programming commonly uses a table of size \(m\times n\).

When every cell is calculated once and each calculation takes constant time:

- Time complexity: \(O(mn)\).
- Space complexity: \(O(mn)\).

Some DP problems can optimize space by keeping only the previous row, reducing auxiliary space to \(O(n)\).