## Question

Find the time and auxiliary space complexity.

```python
def divide(n):
    if n <= 1:
        return

    for i in range(n):
        print(i)

    divide(n // 3)
    divide(2 * n // 3)
```

## Answer

- **Time Complexity:** \(O(n\log n)\)
- **Auxiliary Space Complexity:** \(O(\log n)\)

## Detailed Explanation

**Step 1: Analyze the loop**

The loop performs \(n\) operations.

Cost:

\[
O(n)
\]

**Step 2: Analyze recursive calls**

The function divides the input into two unequal parts:

- First part: approximately \(n/3\).
- Second part: approximately \(2n/3\).

The recurrence is:

\[
T(n)=T(n/3)+T(2n/3)+O(n)
\]

**Step 3: Analyze the recursion tree**

At every level, the total size of the subproblems is approximately \(n\).

For example:

\[
n/3+2n/3=n
\]

Therefore, the total work per level is \(O(n)\).

**Step 4: Calculate the number of levels**

The longest path repeatedly follows the larger subproblem:

\[
n,\frac{2n}{3},\left(\frac23\right)^2n,\ldots
\]

It takes \(O(\log n)\) levels to reach the base case.

Therefore:

\[
O(n)\times O(\log n)
\]

\[
\boxed{O(n\log n)}
\]

**Step 5: Calculate auxiliary space**

Only one recursive path is active at a time.

The maximum recursion depth is \(O(\log n)\).

Therefore:

\[
\boxed{O(\log n)}
\]

## Key Takeaway

Unequal recursive divisions can still have \(O(n\log n)\) time complexity when the total subproblem size at each level remains \(O(n)\).