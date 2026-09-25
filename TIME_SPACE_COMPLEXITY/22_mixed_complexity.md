## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    print(i)

j = 1

while j < n:
    j = j * 2
    print(j)
```

---

## Explanation

This code contains **two separate loops**.

---

### Step 1 — First loop

```python
for i in range(n):
```

This runs `n` times.

Therefore:

```text
O(n)
```

---

### Step 2 — Second loop

The second loop is:

```python
while j < n:
    j = j * 2
```

The value of `j` doubles:

```text
1 → 2 → 4 → 8 → 16 → ...
```

Therefore, it takes approximately:

```text
log₂(n)
```

iterations.

So:

```text
O(log n)
```

---

### Step 3 — Combine the two loops

The loops are **consecutive**, not nested.

Therefore, we add their complexities:

```text
O(n) + O(log n)
```

Now compare the growth rates.

For large values of `n`:

```text
n grows much faster than log n
```

Therefore, `O(n)` is the dominant term.

So:

```text
O(n + log n)
```

simplifies to:

```text
O(n)
```

## 🧠 Important Rule

When combining different complexities:

```text
O(n) + O(log n) = O(n)

O(n²) + O(n) = O(n²)

O(n³) + O(n²) = O(n³)
```

The **dominant/highest-growing term** determines the final Big-O.

## ✅ Final Answer

**Time Complexity: `O(n)`**

**Reason:** The first loop takes `O(n)` and the second takes `O(log n)`. Since they are consecutive, we add them, and `O(n)` dominates `O(log n)`.
