## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    print(i)
```

---

## Explanation

### Step 1 — Understand the loop

The loop is:

```python
for i in range(n):
```

`range(n)` starts from `0` and goes up to `n - 1`.

For example, if:

```text
n = 5
```

The values of `i` will be:

```text
0 → 1 → 2 → 3 → 4
```

So, the loop executes **5 times**.

---

### Step 2 — What happens when `n` increases?

If:

```text
n = 10     → 10 iterations
n = 100    → 100 iterations
n = 1000   → 1000 iterations
```

Therefore, the number of operations increases directly with `n`.

We can represent the number of operations as:

```text
n
```

---

### Step 3 — Find the Big O

Since the loop runs `n` times:

```text
Time Complexity = O(n)
```

This is called **Linear Time Complexity** because the running time grows linearly with the input size.

---

## 🧠 Key Point

A single loop that runs from `0` to `n - 1` generally has:

```text
O(n)
```

---

## ✅ Final Answer

**Time Complexity: `O(n)`**

**Reason:** The loop executes exactly `n` times, and each iteration performs a constant-time operation.
