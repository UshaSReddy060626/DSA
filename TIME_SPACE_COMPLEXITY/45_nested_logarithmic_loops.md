## 📝 Question

Find the Time Complexity:

```python
i = 1

while i < n:
    j = 1

    while j < n:
        print(i, j)
        j *= 2

    i *= 2
```

## ✅ Answer

**O((log n)²)**

## Explanation

### Step 1 — Analyze the outer loop

```python
i *= 2
```

The value of `i` doubles:

```text
1 → 2 → 4 → 8 → 16 → ...
```

It takes approximately \(\log_2 n\) iterations.

Therefore, the outer loop is **O(log n)**.

### Step 2 — Analyze the inner loop

For each outer iteration, `j` is reset to 1.

Then:

```python
j *= 2
```

The values of `j` also double:

```text
1 → 2 → 4 → 8 → 16 → ...
```

The inner loop runs approximately \(\log_2 n\) times per outer iteration.

Therefore, the inner loop is **O(log n)**.

### Step 3 — Multiply the complexities

The loops are nested:

\[
O(\log n)\times O(\log n)
\]

Therefore:

\[
\boxed{O((\log n)^2)}
\]

### 💡 Key Idea

Two nested loops that each double their loop variable produce **O((log n)²)**.

Remember: `j = 1` is executed again during every outer iteration, so the inner loop repeats its logarithmic work each time.

**Final Answer: O((log n)²)**