## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    j = 1

    while j < n:
        j *= 3
```

## ✅ Answer

**O(n log n)**

## Explanation

### Step 1 — Outer loop

```python
for i in range(n):
```

Runs `n` times.

Complexity: **O(n)**.

### Step 2 — Inner loop

```python
j = 1
while j < n:
    j *= 3
```

The values of `j` are:

```text
1 → 3 → 9 → 27 → 81 → ...
```

After `t` iterations, the value is approximately:

\[
j=3^t
\]

The loop stops when \(3^t\ge n\).

Taking logarithms gives:

\[
t\approx\log_3 n
\]

Therefore, the inner loop is **O(log n)**.

### Step 3 — Multiply

The inner loop repeats for every outer iteration:

\[
O(n)\times O(\log n)
\]

Therefore:

\[
\boxed{O(n\log n)}
\]

## 💡 Key Idea

The base of the logarithm does not matter in Big O notation.

Both doubling and tripling give logarithmic complexity:

- `j *= 2` → O(log n)
- `j *= 3` → O(log n)
- `j *= 10` → O(log n)

**Final Answer: O(n log n)**