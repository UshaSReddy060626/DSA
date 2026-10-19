## Question

Find the time complexity of the following binary search implementation.

```python
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1
```

Assume `arr` is sorted.

## Answer

- **Best case:** \(O(1)\)
- **Worst case:** \(O(\log n)\)

## Explanation

### Step 1: Understand binary search

Binary search finds an element in a sorted list by repeatedly dividing the search range into approximately two halves.

For example, if the list contains 16 elements:

- First step: search among at most 16 elements.
- Second step: search among at most 8 elements.
- Third step: search among at most 4 elements.
- Fourth step: search among at most 2 elements.
- Fifth step: search among at most 1 element.

### Step 2: Analyze the loop

After each unsuccessful comparison, the algorithm discards approximately half of the remaining elements.

The search size changes like this:

\[
n,\frac{n}{2},\frac{n}{4},\frac{n}{8},\ldots
\]

The number of times we can halve `n` before reaching `1` is approximately \(\log_2 n\).

Therefore, the worst-case complexity is:

\[
\boxed{O(\log n)}
\]

### Step 3: Understand the best case

If the target is exactly at the middle of the list during the first comparison, the function returns immediately.

That takes constant time:

\[
\boxed{O(1)}
\]

## Key Takeaway

Binary search is \(O(\log n)\) because it reduces the search space by half during every iteration.

**Important interview point:** Binary search requires sorted data. Searching a Python list by index is constant-time, but finding an arbitrary target in an unsorted list generally requires \(O(n)\) time.