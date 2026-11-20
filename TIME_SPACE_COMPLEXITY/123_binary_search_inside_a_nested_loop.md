## Question

Find the time and auxiliary space complexity.

```python
def process(arr):
    n = len(arr)

    for i in range(n):
        low = 0
        high = n - 1

        while low <= high:
            mid = (low + high) // 2

            if arr[mid] == arr[i]:
                break
            elif arr[mid] < arr[i]:
                low = mid + 1
            else:
                high = mid - 1
```

Assume the array is sorted in ascending order.

## Answer

- **Time Complexity:** \(O(n\log n)\)
- **Auxiliary Space Complexity:** \(O(1)\)

## Detailed Explanation

**Step 1: Analyze the outer loop**

The outer loop visits every element.

It executes \(n\) times.

**Step 2: Analyze the inner while loop**

The inner loop performs binary search.

In every iteration, the search interval is reduced approximately by half.

For an array of size \(n\):

\[
O(\log n)
\]

**Step 3: Calculate total time**

The binary search is performed once for every outer-loop iteration.

Therefore:

\[
O(n)\times O(\log n)
\]

\[
\boxed{O(n\log n)}
\]

**Step 4: Calculate auxiliary space**

Only a fixed number of variables are used:

- `i`
- `low`
- `high`
- `mid`

No additional arrays or recursive calls are created.

Therefore:

\[
\boxed{O(1)}
\]

## Key Takeaway

When binary search is placed inside a loop that executes \(n\) times, the overall time complexity is generally \(O(n\log n)\).