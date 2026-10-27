## Question

Find the total time complexity of this code, which builds a prefix sum array and answers `q` range-sum queries.

```python
def range_sums(arr, queries):
    n = len(arr)
    prefix = [0] * (n + 1)

    for i in range(n):
        prefix[i + 1] = prefix[i] + arr[i]

    results = []

    for left, right in queries:
        results.append(prefix[right + 1] - prefix[left])

    return results
```

Assume `arr` contains `n` elements and `queries` contains `q` queries. Each query has valid indices, with `left <= right`.

## Answer

- **Time Complexity:** \(O(n+q)\)
- **Auxiliary Space:** \(O(n+q)\), including the prefix array and results.

## Explanation

### Step 1: Build the prefix sum array

```python
for i in range(n):
    prefix[i + 1] = prefix[i] + arr[i]
```

This loop visits each element once.

Time complexity:

\[
O(n)
\]

### Step 2: Answer each query

```python
prefix[right + 1] - prefix[left]
```

Each range sum is calculated using one subtraction and two array accesses. These take \(O(1)\) time per query.

For `q` queries, the total time is:

\[
O(q)
\]

### Step 3: Combine both stages

The prefix array is built first, then all queries are answered.

\[
T(n,q)=O(n)+O(q)
\]

Therefore:

\[
\boxed{O(n+q)}
\]

The prefix array requires \(O(n)\) space, while the results list requires \(O(q)\) space.

## Key Takeaway

Preprocessing can make repeated queries faster.

Without prefix sums, answering each range-sum query by scanning its elements can take up to \(O(n)\) time. With prefix sums, each query takes \(O(1)\) after an \(O(n)\) setup.

This is a common pattern in array and competitive-programming interviews.