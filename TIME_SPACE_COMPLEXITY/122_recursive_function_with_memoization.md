## Question

Find the time and auxiliary space complexity.

```python
def fib(n, memo):
    if n <= 1:
        return n

    if n in memo:
        return memo[n]

    memo[n] = fib(n - 1, memo) + fib(n - 2, memo)

    return memo[n]
```

Assume the function is initially called with an empty dictionary.

## Answer

- **Time Complexity:** \(O(n)\) average
- **Auxiliary Space Complexity:** \(O(n)\)

## Detailed Explanation

**Step 1: Understand the recursion**

The function calculates Fibonacci numbers using two recursive calls:

\[
F(n)=F(n-1)+F(n-2)
\]

Without memoization, many values would be calculated repeatedly.

**Step 2: Understand memoization**

The dictionary stores previously calculated Fibonacci values.

For example:

- Calculate `fib(5)`.
- Store its result.
- If `fib(5)` is requested again, return the stored result instead of calculating it again.

**Step 3: Calculate time complexity**

Each Fibonacci value from 0 to n is calculated at most once.

There are approximately \(n\) distinct values.

Dictionary lookup and insertion take \(O(1)\) average time.

Therefore:

\[
\boxed{O(n)}
\]

**Step 4: Calculate auxiliary space**

The dictionary stores up to \(n\) results.

The recursion stack can also reach depth \(O(n)\).

Therefore:

\[
O(n)+O(n)=\boxed{O(n)}
\]

## Key Takeaway

Memoization reduces repeated recursive calculations. It can change Fibonacci's time complexity from exponential to linear, while requiring additional memory.