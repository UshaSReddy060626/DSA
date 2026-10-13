## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(i, n * n):
        print(i, j)
```

## ✅ Answer

**O(n³)**

## Explanation

### Step 1 — Outer loop

```python
for i in range(n):
```

The outer loop runs `n` times.

### Step 2 — Inner loop

```python
for j in range(i, n * n):
```

The inner loop starts at `i` and ends just before `n * n`.

For each outer iteration, it runs at most \(n^2\) times.

Its iteration count is approximately \(n^2-i\).

### Step 3 — Calculate the total

The total number of executions is:

\[
\sum_{i=0}^{n-1}(n^2-i)
\]

Expanding the sum:

\[
n\cdot n^2-\frac{n(n-1)}{2}
\]

\[
=n^3-\frac{n(n-1)}{2}
\]

The leading term is \(n^3\). The remaining terms grow more slowly.

Therefore:

\[
T(n)=O(n^3)
\]

## 💡 Key Idea

Do not assume the inner loop always runs exactly `n` times.

Read its actual range. Here, the inner loop runs approximately \(n^2\) times per outer iteration, giving a total cubic growth rate.

**Final Answer: O(n³)**