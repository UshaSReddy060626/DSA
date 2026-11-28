## Question

Find the time and auxiliary space complexity of the following algorithm.

The algorithm finds the maximum element in every window of size `k`.

```python
from collections import deque

def sliding_maximum(arr, k):
    dq = deque()
    result = []

    for i in range(len(arr)):
        while dq and dq[0] <= i - k:
            dq.popleft()

        while dq and arr[dq[-1]] <= arr[i]:
            dq.pop()

        dq.append(i)

        if i >= k - 1:
            result.append(arr[dq[0]])

    return result
```

Let \(n\) be the length of the array and \(k\) be the window size.

## Answer

- **Time Complexity:** \(O(n)\)
- **Auxiliary Space Complexity:** \(O(k)\), excluding the output list.

## Explanation

### Step 1: Understand the outer loop

```python
for i in range(len(arr)):
```

The loop processes all \(n\) elements.

### Step 2: Understand the first while loop

```python
while dq and dq[0] <= i - k:
    dq.popleft()
```

This removes indices that are outside the current window.

An element can enter the deque once and leave it at most once.

### Step 3: Understand the second while loop

```python
while dq and arr[dq[-1]] <= arr[i]:
    dq.pop()
```

This removes smaller elements from the back of the deque.

Although this is a nested while loop, each index is inserted only once and removed at most once.

Across the entire algorithm, the total number of deque operations is \(O(n)\), not \(O(n^2)\).

### Step 4: Calculate total time

- Each element is inserted once.
- Each element is removed at most once.
- Each iteration performs constant additional work.

Therefore:

\[
\boxed{O(n)}
\]

### Step 5: Calculate space

The deque stores indices belonging to the current window.

At most \(k\) indices are stored.

Therefore, auxiliary space is:

\[
\boxed{O(k)}
\]

The result list can contain \(n-k+1\) elements, so including output space, total space is \(O(n)\).

## Key Takeaway

Nested while loops do not automatically mean \(O(n^2)\).

When each element can be inserted and removed only a limited number of times, use amortized analysis.

This algorithm takes \(O(n)\) time despite having nested loops.