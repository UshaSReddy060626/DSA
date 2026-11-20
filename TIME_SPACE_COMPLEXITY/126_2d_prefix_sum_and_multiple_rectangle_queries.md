## Question

Find the time and auxiliary space complexity of the following code.

```python
def rectangle_queries(matrix, queries):
    rows = len(matrix)
    cols = len(matrix[0])

    prefix = [[0] * (cols + 1) for _ in range(rows + 1)]

    for i in range(1, rows + 1):
        for j in range(1, cols + 1):
            prefix[i][j] = (
                matrix[i - 1][j - 1]
                + prefix[i - 1][j]
                + prefix[i][j - 1]
                - prefix[i - 1][j - 1]
            )

    results = []

    for r1, c1, r2, c2 in queries:
        total = (
            prefix[r2 + 1][c2 + 1]
            - prefix[r1][c2 + 1]
            - prefix[r2 + 1][c1]
            + prefix[r1][c1]
        )
        results.append(total)

    return results
```

Let:
- \(r\) = number of rows
- \(c\) = number of columns
- \(q\) = number of rectangle queries

## Answer

- **Time Complexity:** \(O(rc+q)\)
- **Auxiliary Space Complexity:** \(O(rc+q)\), including the results list.

## Explanation

### Step 1: Create the prefix matrix

```python
prefix = [[0] * (cols + 1) for _ in range(rows + 1)]
```

A new matrix of size approximately \(r \times c\) is created.

Space:

\[
O(rc)
\]

### Step 2: Build the prefix matrix

```python
for i in range(1, rows + 1):
    for j in range(1, cols + 1):
```

The outer loop runs \(r\) times.

The inner loop runs \(c\) times.

Total iterations:

\[
r \times c
\]

Each iteration performs a constant number of arithmetic operations.

Time:

\[
O(rc)
\]

### Step 3: Process rectangle queries

```python
for r1, c1, r2, c2 in queries:
```

This loop runs \(q\) times.

Inside each iteration, only four prefix values are accessed and combined.

Each query takes:

\[
O(1)
\]

For all queries:

\[
O(q)
\]

### Step 4: Calculate total time

Prefix construction:

\[
O(rc)
\]

Query processing:

\[
O(q)
\]

Therefore:

\[
\boxed{O(rc+q)}
\]

### Step 5: Calculate space

- Prefix matrix: \(O(rc)\)
- Results list: \(O(q)\)

Therefore, including returned results:

\[
\boxed{O(rc+q)}
\]

If the question asks for auxiliary space excluding the output list, the answer is \(O(rc)\).

## Key Takeaway

A 2D Prefix Sum helps answer rectangle-sum queries in constant time after preprocessing.

Remember:

- Building prefix matrix: \(O(rc)\)
- One rectangle query: \(O(1)\)
- \(q\) queries: \(O(q)\)
- Total: \(O(rc+q)\)