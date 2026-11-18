## Question

Find the time and auxiliary space complexity.

```python
def mystery(n):
    if n <= 1:
        return

    for i in range(n):
        print(i)

    mystery(n // 2)
    mystery(n // 4)
```

## Answer

- **Time Complexity:** \(O(n)\)
- **Auxiliary Space Complexity:** \(O(\log n)\)

## Detailed Explanation

**Step 1: Analyze the loop**

The loop executes \(n\) times.

Its cost is:

\[
O(n)
\]

**Step 2: Analyze recursive calls**

The function makes two recursive calls:

- One with \(n/2\).
- One with \(n/4\).

The recurrence is:

\[
T(n)=T(n/2)+T(n/4)+O(n)
\]

**Step 3: Calculate total work**

At the first level, work is \(n\).

At the next level, total work is:

\[
n/2+n/4=3n/4
\]

At every following level, the total work decreases geometrically.

Therefore:

\[
T(n)=O(n+n(3/4)+n(3/4)^2+\cdots)
\]

The geometric series is bounded by a constant multiple of \(n\).

Hence:

\[
\boxed{O(n)}
\]

**Step 4: Calculate auxiliary space**

The longest recursive path repeatedly divides the input by 2:

\[
n,\ n/2,\ n/4,\ n/8,\ldots
\]

This gives \(O(\log n)\) maximum recursion depth.

Therefore, auxiliary space is \(O(\log n)\).

## Key Takeaway

When recursive calls use different input sizes, add their work together. For auxiliary space, consider the maximum active recursion depth, not the total number of recursive calls.