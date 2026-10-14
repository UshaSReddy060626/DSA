## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    j = n

    while j > 1:
        print(i, j)
        j = j // 2
```

## ✅ Answer

**O(n log n)**

## Explanation

### Step 1 — Analyze the outer loop

```python
for i in range(n):
```

The outer loop executes `n` times.

Its complexity is **O(n)**.

### Step 2 — Analyze the inner loop

```python
j = n

while j > 1:
    j = j // 2
```

The value of `j` is repeatedly divided by 2.

For example, if `n = 32`:

```text
32 → 16 → 8 → 4 → 2 → 1
```

The number of iterations is approximately \(\log_2 n\).

Therefore, the inner loop has complexity **O(log n)**.

### Step 3 — Combine the loops

The inner loop runs for every outer-loop iteration.

\[
T(n)=n\log n
\]

Therefore:

\[
\boxed{O(n\log n)}
\]

## 💡 Key Idea

When a linear loop contains a loop that repeatedly halves its variable, multiply their complexities:

\[
O(n)\times O(\log n)=O(n\log n)
\]

**Final Answer: O(n log n)**