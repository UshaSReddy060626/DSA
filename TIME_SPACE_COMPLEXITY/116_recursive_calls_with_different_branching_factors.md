## Question

Find the time and auxiliary space complexity.

```python
def solve(n):
    if n <= 1:
        return

    solve(n // 2)
    solve(n // 2)
    solve(n // 2)

    for i in range(n):
        print(i)
```

## Answer

- **Time Complexity:** \(O(n\log n)\)
- **Auxiliary Space Complexity:** \(O(\log n)\)

## Detailed Explanation

**Step 1: Analyze the recursive calls**

There are three recursive calls, each with input size \(n/2\).

**Step 2: Analyze the loop**

The loop executes \(n\) times, giving \(O(n)\) work per call.

**Step 3: Form the recurrence**

\[
T(n)=3T(n/2)+O(n)
\]

Using the Master Theorem:

- \(a=3\)
- \(b=2\)
- \(f(n)=n\)

Calculate:

\[
n^{\log_2 3}
\]

Since \(n\) grows slower than \(n^{\log_2 3}\):

\[
T(n)=O(n^{\log_2 3})
\]

Therefore, the tighter complexity is:

\[
\boxed{\Theta(n^{\log_2 3})}
\]

**Step 4: Calculate auxiliary space**

The maximum recursion depth is:

\[
\log_2 n
\]

Each active call uses constant local space, so:

\[
\boxed{O(\log n)}
\]

## Key Takeaway

When a function makes three recursive calls on half-sized inputs, do not assume \(O(n\log n)\). Count the branching factor using the recurrence.