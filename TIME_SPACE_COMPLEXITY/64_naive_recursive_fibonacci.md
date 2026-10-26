## Question

Find the time complexity of this recursive function.

```python
def fibonacci(n):
    if n <= 1:
        return n

    return fibonacci(n - 1) + fibonacci(n - 2)
```

## Answer

**Time Complexity: \(O(2^n)\)** as a common upper bound.

A tighter bound is \(\Theta(\varphi^n)\), where \(\varphi \approx 1.618\).

## Explanation

### Step 1: Understand the recursive calls

For each `n` greater than `1`, the function calls itself twice:

```python
fibonacci(n - 1)
fibonacci(n - 2)
```

Each of these calls may create more recursive calls.

### Step 2: Visualize the recursion

For `fibonacci(5)`, the function begins by evaluating:

```text
fibonacci(5)
├── fibonacci(4)
│   ├── fibonacci(3)
│   └── fibonacci(2)
└── fibonacci(3)
    ├── fibonacci(2)
    └── fibonacci(1)
```

Notice that values such as `fibonacci(3)` and `fibonacci(2)` are calculated repeatedly.

### Step 3: Determine the complexity

The recurrence is:

\[
T(n)=T(n-1)+T(n-2)+O(1)
\]

The number of calls grows exponentially with `n`.

A commonly used upper bound is:

\[
\boxed{O(2^n)}
\]

The tighter asymptotic bound is:

\[
\boxed{\Theta(\varphi^n)}
\]

## Key Takeaway

Multiple recursive calls can lead to exponential time, especially when the same subproblems are repeatedly calculated.

Memoization or dynamic programming stores previously calculated Fibonacci values and reduces the time complexity to \(O(n)\).