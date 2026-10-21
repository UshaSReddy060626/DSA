## Question

Find the time complexity of this recursive function.

```python
def fun(n):
    if n <= 1:
        return

    fun(n // 2)
    fun(n // 2)
```

## Answer

**Time Complexity: \(O(n)\)**

## Explanation

### Step 1: Understand the base case

```python
if n <= 1:
    return
```

When `n` becomes `1` or smaller, the function stops making recursive calls.

### Step 2: Count the recursive calls

Each call makes two new calls, and each receives approximately half the original input.

The recurrence is:

\[
T(n)=2T(n/2)+O(1)
\]

### Step 3: Build the recursion levels

Suppose the original input is `n`.

- Level 0: 1 call of size `n`.
- Level 1: 2 calls of size `n/2`.
- Level 2: 4 calls of size `n/4`.
- Level 3: 8 calls of size `n/8`.

The number of calls doubles at each level, while each call's input size halves.

The recursion has approximately \(\log_2 n\) levels.

At the final level, there are approximately `n` small calls. Summing the calls across levels gives a geometric series:

\[
1+2+4+\cdots+n=O(n)
\]

Therefore:

\[
\boxed{O(n)}
\]

## Key Takeaway

Two recursive calls do not automatically mean exponential time. You must consider how the input size changes in each call.

- Two calls on `n - 1`: often exponential.
- Two calls on `n // 2`: \(O(n)\) when each call does only constant additional work.

The important factors are the number of recursive calls and the size of each subproblem.