## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    print(i)

for j in range(n):
    print(j)
```

---

## Explanation

There are **two separate loops**.

### Step 1 — Analyze the first loop

```python
for i in range(n):
    print(i)
```

This loop runs `n` times.

Therefore:

```text
O(n)
```

### Step 2 — Analyze the second loop

```python
for j in range(n):
    print(j)
```

This also runs `n` times.

Therefore:

```text
O(n)
```

### Step 3 — Add the complexities

Since the loops are **consecutive**, we add them:

```text
O(n) + O(n)
```

```text
= O(2n)
```

Constants are ignored in Big O:

```text
= O(n)
```

## ✅ Final Answer

**Time Complexity: `O(n)`**

**Key Rule:** Consecutive loops are generally **added**, not multiplied.
