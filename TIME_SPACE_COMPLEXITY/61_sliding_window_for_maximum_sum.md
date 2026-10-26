## Question

Find the time complexity of this code.

```python
def max_window_sum(arr, k):
    n = len(arr)

    if k > n or k <= 0:
        return None

    window_sum = sum(arr[:k])
    maximum = window_sum

    for i in range(k, n):
        window_sum += arr[i] - arr[i - k]
        maximum = max(maximum, window_sum)

    return maximum
```

Assume the array contains `n` elements and the window size is `k`.

## Answer

**Time Complexity: \(O(n)\)**

## Explanation

### Step 1: Calculate the first window

```python
window_sum = sum(arr[:k])
```

The first `k` elements are added together, requiring \(O(k)\) time.

### Step 2: Slide the window

```python
window_sum += arr[i] - arr[i - k]
```

Instead of adding all `k` elements again, the algorithm:

- Adds the new element entering the window.
- Subtracts the element leaving the window.

Each update takes \(O(1)\) time.

The loop runs approximately \(n-k\) times.

### Step 3: Combine the work

\[
T(n,k)=O(k)+O(n-k)
\]

Therefore:

\[
\boxed{O(n)}
\]

More precisely, the complexity is \(O(n)\) for valid \(1\leq k\leq n\).

## Key Takeaway

A sliding window avoids recalculating the entire window each time.

A straightforward approach might take \(O(nk)\), while this optimized approach takes \(O(n)\).

When processing consecutive subarrays or substrings, look for a way to update the previous result instead of recalculating everything.