## Question

Find the time and auxiliary space complexity.

```python
def process(arr):
    n = len(arr)
    freq = {}

    for i in range(n):
        for j in range(i, n):
            if arr[j] in freq:
                freq[arr[j]] += 1
            else:
                freq[arr[j]] = 1

    for key in freq:
        print(key, freq[key])
```

Assume dictionary lookup and insertion take \(O(1)\) average time.

## Answer

- **Average Time Complexity:** \(O(n^2)\)
- **Worst-Case Time Complexity:** \(O(n^2)\) under the usual assumption of efficient dictionary operations; pathological hash collisions can increase it.
- **Auxiliary Space Complexity:** \(O(n)\)

## Detailed Explanation

**Step 1: Analyze the nested loops**

The outer loop runs \(n\) times.

The inner loop runs:

\[
n+(n-1)+(n-2)+\cdots+1
\]

Using the sum formula:

\[
\frac{n(n+1)}{2}=O(n^2)
\]

**Step 2: Analyze dictionary operations**

Each iteration performs a dictionary lookup and possibly an insertion or update.

These operations take \(O(1)\) average time.

Therefore, the nested loops take:

\[
O(n^2)
\]

**Step 3: Analyze the final loop**

The dictionary contains at most \(n\) distinct keys.

Therefore, this loop takes \(O(n)\).

**Step 4: Calculate total time**

\[
O(n^2)+O(n)=\boxed{O(n^2)}
\]

**Step 5: Calculate auxiliary space**

The dictionary stores at most \(n\) distinct elements.

Therefore:

\[
\boxed{O(n)}
\]

## Key Takeaway

A hash map does not automatically make an algorithm \(O(1)\). You must count how many times its operations are performed.