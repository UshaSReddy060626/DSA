## Question

Find the time and auxiliary space complexities of this code.

```python
def sum_matrix(matrix):
    total = 0

    for row in matrix:
        for value in row:
            total += value

    return total
```

Assume the matrix has `r` rows and `c` columns.

## Answer

- **Time Complexity:** \(O(rc)\)
- **Auxiliary Space:** \(O(1)\)

## Explanation

### Step 1: Understand the matrix

A matrix contains rows and columns. If it has `r` rows and `c` columns, the total number of elements is:

\[
r\times c
\]

### Step 2: Count the operations

The outer loop visits each of the `r` rows. For every row, the inner loop visits its `c` elements.

Therefore, the total number of additions is:

\[
r\times c
\]

So the time complexity is:

\[
\boxed{O(rc)}
\]

### Step 3: Calculate auxiliary space

The function uses only the variables `total`, `row`, and `value`, regardless of the matrix size.

It does not create another matrix or a collection that grows with the input.

Therefore:

\[
\boxed{O(1)}
\]

## Key Takeaway

For a matrix with `r` rows and `c` columns, traversing every element takes \(O(rc)\) time.

If the matrix is square, with `n` rows and `n` columns, the complexity becomes \(O(n^2)\).