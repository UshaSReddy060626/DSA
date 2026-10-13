## 📝 Question

Find the Time Complexity in terms of `n` and `m`.

```python
for i in range(n):
    print(i)

for j in range(m):
    print(j)
```

## ✅ Answer

**O(n + m)**

## Explanation

### Step 1 — Analyze the first loop

```python
for i in range(n):
```

This loop runs `n` times.

Its complexity is **O(n)**.

### Step 2 — Analyze the second loop

```python
for j in range(m):
```

This loop runs `m` times.

Its complexity is **O(m)**.

### Step 3 — Add the complexities

The loops execute one after another, so we add their costs:

\[
T(n,m)=O(n)+O(m)
\]

Therefore:

\[
\boxed{O(n+m)}
\]

### 💡 Key Idea

When two consecutive loops have different input sizes, don't automatically write O(n).

- First loop depends on `n`.
- Second loop depends on `m`.
- Their total work depends on both.

If `m = n`, the result simplifies to O(n).

**Final Answer: O(n + m)**