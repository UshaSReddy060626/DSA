## 📝 Question

Find the Time Complexity:

```python
i = 1

while i < n:
    print(i)
    i = i * 2

    if i > n // 2:
        break
```

## ✅ Answer

**O(log n)**

## Explanation

### Step 1 — Understand the loop

The variable `i` doubles every iteration:

```text
1 → 2 → 4 → 8 → 16 → 32 → ...
```

Without the `break`, the loop would run approximately \(\log_2 n\) times.

### Step 2 — Understand the `break`

The loop stops early when:

```python
if i > n // 2:
    break
```

This condition only reduces the number of iterations by a constant amount. It does not change the logarithmic growth rate.

For example, if `n = 64`, the values of `i` double until the condition stops the loop.

### Step 3 — Calculate the complexity

Because the variable doubles each time, the number of iterations grows logarithmically.

\[
T(n)=O(\log n)
\]

## 💡 Key Idea

When a loop variable doubles or halves on each iteration, look for **O(log n)**, even if the loop contains a `break` that stops it a little earlier.

**Final Answer: O(log n)**