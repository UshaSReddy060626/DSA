## Question

Find the time complexity of this code.

```python
def count_steps(arr):
    steps = 0

    for x in arr:
        while x > 1:
            x //= 2
            steps += 1

    return steps
```

Assume `arr` contains `n` positive integers, and let `M` be the largest integer in the array.

## Answer

**Time Complexity: \(O(n\log M)\)**

## Explanation

### Step 1: Analyze the inner loop

```python
while x > 1:
    x //= 2
```

The value of `x` is divided by two on every iteration.

For example, if `x = 16`, its values are:

```text
16 → 8 → 4 → 2 → 1
```

It takes approximately \(\log_2 x\) iterations to reach `1`.

### Step 2: Analyze the outer loop

The outer loop processes all `n` elements.

Each element may require a different number of inner-loop iterations, depending on its value.

The total work is proportional to:

\[
\sum_{x\in arr} O(\log x)
\]

### Step 3: Use the largest value

Since every element is at most `M`, each inner loop runs at most \(O(\log M)\) times.

There are `n` elements, so:

\[
T(n,M)=O(n\log M)
\]

Therefore:

\[
\boxed{O(n\log M)}
\]

## Key Takeaway

Sometimes complexity depends on both the number of elements and their values.

- `n` = number of elements.
- `M` = largest value.
- Outer loop: \(n\) iterations.
- Inner loop: up to \(\log M\) iterations per element.

If all values are bounded by a constant, the total is \(O(n)\). If the maximum value can grow, keep the logarithmic factor.