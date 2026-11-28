## Question

Find the time and auxiliary space complexity of the following algorithm.

It preprocesses an array into a Sparse Table and answers multiple range minimum queries.

```python
def sparse_table(arr, queries):
    n = len(arr)
    log = [0] * (n + 1)

    for i in range(2, n + 1):
        log[i] = log[i // 2] + 1

    levels = n.bit_length()
    st = [[0] * n for _ in range(levels)]

    st[0] = arr[:]

    for j in range(1, levels):
        for i in range(n - (1 << j) + 1):
            st[j][i] = min(
                st[j - 1][i],
                st[j - 1][i + (1 << (j - 1))]
            )

    result = []

    for left, right in queries:
        length = right - left + 1
        j = log[length]

        answer = min(
            st[j][left],
            st[j][right - (1 << j) + 1]
        )

        result.append(answer)

    return result
```

Let:
- \(n\) = number of array elements
- \(q\) = number of queries

Assume every query asks for the minimum over an inclusive range \([left,right]\).

## Answer

- **Time Complexity:** \(O(n\log n+q)\)
- **Auxiliary Space Complexity:** \(O(n\log n)\), excluding the output list.

## Explanation

### Step 1: Create the logarithm array

```python
log = [0] * (n + 1)
```

This takes \(O(n)\) time and space.

The following loop also runs \(O(n)\) times:

```python
for i in range(2, n + 1):
```

### Step 2: Create the Sparse Table

```python
st = [[0] * n for _ in range(levels)]
```

The number of levels is:

\[
O(\log n)
\]

Each level contains up to \(n\) positions.

Therefore, space is:

\[
O(n\log n)
\]

### Step 3: Build the table

```python
for j in range(1, levels):
    for i in range(n - (1 << j) + 1):
```

- Outer loop: \(O(\log n)\)
- Inner loop: at most \(O(n)\)

Each iteration performs a constant-time minimum operation.

Therefore:

\[
\boxed{O(n\log n)}
\]

### Step 4: Process queries

```python
for left, right in queries:
```

There are \(q\) queries.

Each query performs:
- One subtraction.
- One logarithm-array lookup.
- Two Sparse Table lookups.
- One minimum operation.

All these operations take \(O(1)\).

Therefore:

\[
O(q)
\]

### Step 5: Calculate total time

\[
O(n)+O(n\log n)+O(q)
\]

Removing lower-order terms:

\[
\boxed{O(n\log n+q)}
\]

### Step 6: Calculate space

- Sparse Table: \(O(n\log n)\)
- Logarithm array: \(O(n)\)

Therefore:

\[
\boxed{O(n\log n)}
\]

The output list adds \(O(q)\) space.

## Key Takeaway

Sparse Tables are useful when an array does not change and many range minimum queries must be answered.

- Preprocessing: \(O(n\log n)\)
- One query: \(O(1)\)
- \(q\) queries: \(O(q)\)
- Space: \(O(n\log n)\)

Important: This constant-time query works for idempotent operations such as minimum, maximum, and GCD. It does not directly work for ordinary range sums.