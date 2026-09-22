## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 64

i = 1

while i < n:
    i = i * 2
    print(i)
```

---

## Explanation

The important line is:

```python
i = i * 2
```

The value of `i` doubles after every iteration.

The sequence is:

```text
1 → 2 → 4 → 8 → 16 → 32 → 64
```

The loop therefore does not increase `i` by `1`.

Instead, it **doubles** it each time.

---

### Step 1 — Count the iterations

For `n = 64`:

```text
1 → 2      (1)
2 → 4      (2)
4 → 8      (3)
8 → 16     (4)
16 → 32    (5)
32 → 64    (6)
```

There are approximately:

```text
log₂(64) = 6
```

iterations.

---

### Step 2 — Generalize

For a general value of `n`, the number of iterations is approximately:

```text
log₂(n)
```

Therefore:

```text
O(log n)
```

The base of the logarithm is usually omitted in Big O because changing the base only changes the result by a constant factor.

## 🧠 Remember

If a variable is repeatedly:

```text
× 2
```

or:

```text
÷ 2
```

you should think:

```text
O(log n)
```

## ✅ Final Answer

**Time Complexity: `O(log n)`**
