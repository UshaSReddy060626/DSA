## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(0, n, 2):
    print(i)
```

---

## Explanation

### Step 1 — Understand `range()`

The loop uses:

```python
range(0, n, 2)
```

The three values mean:

```text
0 → Starting value
n → Ending limit
2 → Step size
```

The value of `i` increases by `2` after every iteration.

For example, if:

```text
n = 10
```

The values are:

```text
0 → 2 → 4 → 6 → 8
```

So the loop executes **5 times**.

---

### Step 2 — Calculate the number of iterations

Because `i` increases by `2`, the loop runs approximately:

```text
n / 2
```

times.

For example:

```text
n = 10

10 / 2 = 5 iterations
```

If:

```text
n = 100

100 / 2 = 50 iterations
```

---

### Step 3 — Convert to Big O

Initially, we can write:

```text
O(n / 2)
```

However, `1/2` is a **constant**.

Big O notation focuses on the **growth rate** and ignores constant factors.

Therefore:

```text
O(n / 2)
```

becomes:

```text
O(n)
```

---

### 🧠 Why do we ignore `1/2`?

Suppose we compare:

```text
n
```

with:

```text
n / 2
```

Both grow at the same general rate when `n` becomes larger.

For example:

```text
n = 1000

n     = 1000
n / 2 = 500
```

The second algorithm performs fewer operations, but its growth is still **linear**.

Therefore, both are classified as:

```text
O(n)
```

---

## ✅ Final Answer

**Time Complexity: `O(n)`**

**Reason:** The loop executes approximately `n/2` times. Since `1/2` is a constant factor, it is ignored in Big O notation, resulting in `O(n)`.
