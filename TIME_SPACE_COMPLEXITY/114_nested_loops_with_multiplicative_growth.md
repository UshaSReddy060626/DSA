## Question

Find the time and auxiliary space complexity.

```python
def calculate(n):
    i = 1

    while i < n:
        j = 1

        while j < n:
            k = 1

            while k < j:
                k *= 2

            j *= 2

        i *= 2
```

## Answer

- **Time Complexity:** \(O((\log n)^3)\)
- **Auxiliary Space Complexity:** \(O(1)\)

## Detailed Explanation

**Step 1: Analyze the outer loop**

```python
i *= 2
```

The value of `i` doubles each time:

\[
1,2,4,8,\ldots,n
\]

Number of iterations:

\[
O(\log n)
\]

**Step 2: Analyze the second loop**

```python
j *= 2
```

Similarly, `j` doubles until it reaches \(n\).

Number of iterations per outer iteration:

\[
O(\log n)
\]

**Step 3: Analyze the innermost loop**

```python
while k < j:
    k *= 2
```

For each value of `j`, `k` doubles until it reaches `j`.

Therefore, the innermost loop runs:

\[
O(\log j)
\]

Since `j` can reach values up to \(n\), this is at most \(O(\log n)\).

**Step 4: Multiply the loop costs**

There are three levels of logarithmic iteration:

\[
O(\log n)\times O(\log n)\times O(\log n)
\]

Therefore:

\[
\boxed{O((\log n)^3)}
\]

**Step 5: Calculate auxiliary space**

Only three variables are used: `i`, `j`, and `k`.

No arrays, recursion, or additional data structures are created.

Therefore:

\[
\boxed{O(1)}
\]

## Key Takeaway

Three nested loops do not necessarily mean \(O(n^3)\). If all three loops double their variables, the complexity can be \(O((\log n)^3)\).