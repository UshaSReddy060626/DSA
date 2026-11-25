## Question

Find the time and auxiliary space complexity of the following algorithm.

The algorithm calculates the Fibonacci number using matrix exponentiation.

```python
def multiply(A, B):
    C = [[0, 0], [0, 0]]

    for i in range(2):
        for j in range(2):
            for k in range(2):
                C[i][j] += A[i][k] * B[k][j]

    return C


def matrix_power(M, n):
    if n == 1:
        return M

    half = matrix_power(M, n // 2)
    result = multiply(half, half)

    if n % 2 == 1:
        result = multiply(result, M)

    return result


def fibonacci(n):
    if n <= 1:
        return n

    M = [[1, 1], [1, 0]]
    result = matrix_power(M, n - 1)

    return result[0][0]
```

Find the complexity in terms of \(n\).

## Answer

- **Time Complexity:** \(O(\log n)\)
- **Auxiliary Space Complexity:** \(O(\log n)\)

## Explanation

### Step 1: Understand matrix multiplication

```python
for i in range(2):
    for j in range(2):
        for k in range(2):
```

There are three nested loops.

However, each loop runs exactly 2 times.

Therefore:

\[
2\times2\times2=8
\]

Only a constant number of operations are performed.

Time complexity:

\[
O(1)
\]

### Step 2: Understand matrix_power()

```python
half = matrix_power(M, n // 2)
```

The function calls itself with half the previous input.

For example, if \(n=16\):

\[
16\rightarrow8\rightarrow4\rightarrow2\rightarrow1
\]

The input is divided by 2 at every recursive call.

Therefore, the recursion depth is:

\[
O(\log n)
\]

### Step 3: Count matrix multiplications

After the recursive call, the algorithm performs:
- One multiplication to square the result.
- One additional multiplication if \(n\) is odd.

At most two matrix multiplications are performed per recursive level.

Each multiplication takes \(O(1)\), because the matrices are always \(2\times2\).

Therefore, work per level is:

\[
O(1)
\]

### Step 4: Calculate total time

There are \(O(\log n)\) recursive levels.

Each level performs constant work.

Thus:

\[
O(\log n)\times O(1)
\]

\[
\boxed{O(\log n)}
\]

### Step 5: Calculate space

Each recursive call remains on the call stack until its result returns.

There are \(O(\log n)\) recursive calls.

The matrices have fixed dimensions, so each uses constant space.

Therefore:

\[
\boxed{O(\log n)}
\]

## Key Takeaway

Matrix exponentiation reduces the number of operations needed to calculate Fibonacci numbers.

- Matrix multiplication for fixed \(2\times2\) matrices: \(O(1)\).
- Input is divided by 2 in each recursive call.
- Number of recursive levels: \(O(\log n)\).
- Total time: \(O(\log n)\).
- Recursion stack: \(O(\log n)\).