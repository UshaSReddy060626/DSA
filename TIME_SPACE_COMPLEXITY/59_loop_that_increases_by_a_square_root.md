## Question

Find the time complexity of this code.

```python
i = 1

while i * i <= n:
    print(i)
    i += 1
```

## Answer

**Time Complexity: \(O(\sqrt n)\)**

## Explanation

### Step 1: Understand the stopping condition

The loop continues while:

```python
i * i <= n
```

This condition is equivalent to:

\[
i \leq \sqrt n
\]

Therefore, `i` only needs to increase until it reaches approximately \(\sqrt n\).

### Step 2: Count the iterations

Suppose `n = 100`.

The loop visits:

```text
1, 2, 3, 4, ..., 10
```

It runs 10 times because \(\sqrt{100}=10\).

If `n = 10,000`, it runs approximately 100 times.

### Step 3: Calculate the complexity

The number of iterations is approximately \(\sqrt n\).

\[
\boxed{O(\sqrt n)}
\]

## Key Takeaway

When a loop increments a variable by a constant but stops when its square reaches `n`, its complexity is \(O(\sqrt n)\).

Recognize these common patterns:

- `i < n` with `i += 1`: \(O(n)\)
- `i * i <= n` with `i += 1`: \(O(\sqrt n)\)
- `i *= 2` with `i < n`: \(O(\log n)\)