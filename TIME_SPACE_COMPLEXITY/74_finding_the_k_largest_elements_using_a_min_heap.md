## Question

Find the time and space complexities of this code.

```python
import heapq

def find_k_largest(arr, k):
    heap = []

    for num in arr:
        heapq.heappush(heap, num)

        if len(heap) > k:
            heapq.heappop(heap)

    return heap
```

Let `n` be the number of elements and `k` be the required number of largest elements, where \(1 \leq k \leq n\).

## Answer

- **Time Complexity:** \(O(n\log k)\)
- **Auxiliary Space:** \(O(k)\)

## Explanation

### Step 1: Understand the heap

The algorithm maintains a min-heap containing at most `k` elements.

Whenever a new number is inserted, the smallest element is removed if the heap becomes larger than `k`.

This ensures that the heap retains the `k` largest elements seen so far.

### Step 2: Analyze insertion

```python
heapq.heappush(heap, num)
```

The heap contains at most `k` elements.

Therefore, insertion takes:

\[
O(\log k)
\]

### Step 3: Analyze removal

```python
if len(heap) > k:
    heapq.heappop(heap)
```

Removing the smallest element also takes:

\[
O(\log k)
\]

Each input element is processed once, so there are `n` iterations.

### Step 4: Calculate total time

\[
T(n,k)=n\times O(\log k)
\]

\[
\boxed{O(n\log k)}
\]

The heap stores at most `k` elements:

\[
\boxed{O(k)}
\]

## Key Takeaway

When you need only the largest or smallest `k` elements, maintaining a heap of size `k` can be more efficient than sorting the entire array.

- Full sorting: \(O(n\log n)\)
- Heap of size `k`: \(O(n\log k)\)

