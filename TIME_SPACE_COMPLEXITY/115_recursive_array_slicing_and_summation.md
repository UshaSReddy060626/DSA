## Question

Find the time and auxiliary space complexity.

```python
def solve(arr):
    n = len(arr)

    if n <= 1:
        return 0

    left = arr[:n // 2]
    right = arr[n // 2:]

    total = 0

    for x in arr:
        total += x

    return solve(left) + solve(right) + total
```

Assume Python list slicing creates new lists and takes time proportional to the slice length.

## Answer

- **Time Complexity:** \(O(n\log n)\)
- **Auxiliary Space Complexity:** \(O(n)\)

## Detailed Explanation

**Step 1: Analyze array slicing**

The function creates two new arrays:

```python
left = arr[:n // 2]
right = arr[n // 2:]
```

Together, these slices copy \(n\) elements.

Cost:

\[
O(n)
\]

**Step 2: Analyze the loop**

```python
for x in arr:
    total += x
```

The loop visits all \(n\) elements.

Cost:

\[
O(n)
\]

**Step 3: Analyze recursion**

The function calls itself twice with arrays of approximately half the size.

The recurrence is:

\[
T(n)=2T(n/2)+O(n)
\]

Using the recursion-tree method:

- Level 1: \(n\) work.
- Level 2: \(n\) total work.
- Level 3: \(n\) total work.
- Number of levels: \(O(\log n)\).

Therefore:

\[
\boxed{O(n\log n)}
\]

**Step 4: Calculate auxiliary space**

At each recursion level, the combined sizes of the newly created slices are approximately \(n\).

However, the arrays created by a parent call remain alive while its recursive calls execute.

The total live copied elements along a deepest path are bounded by:

\[
n+\frac n2+\frac n4+\cdots=O(n)
\]

The recursion stack itself uses \(O(\log n)\) space.

Therefore, total auxiliary space is:

\[
\boxed{O(n)}
\]

## Key Takeaway

Array slicing is not free in Python. When recursive functions repeatedly create slices, count both the copying time and the memory occupied by those new arrays.