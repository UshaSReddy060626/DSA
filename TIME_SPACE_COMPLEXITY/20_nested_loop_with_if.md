## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    for j in range(n):
        if i == j:
            print(i, j)
```

---

## Explanation

### Step 1 — Analyze the outer loop

```python
for i in range(n):
```

This executes `n` times.

```text
O(n)
```

### Step 2 — Analyze the inner loop

For every value of `i`, the inner loop executes:

```python
for j in range(n):
```

`n` times.

Therefore:

```text
O(n) × O(n) = O(n²)
```

### Step 3 — Analyze the `if`

The condition:

```python
if i == j:
```

takes constant time.

```text
O(1)
```

The important point is that **even though `print()` executes only when `i == j`, the inner loop still checks the condition `n` times**.

For example, when `n = 5`:

```text
i = 0 → checks j = 0,1,2,3,4
i = 1 → checks j = 0,1,2,3,4
i = 2 → checks j = 0,1,2,3,4
...
```

There are:

```text
5 × 5 = 25 condition checks
```

### Step 4 — Final complexity

Therefore:

```text
O(n²)
```

The `if` statement does not change the overall complexity.

## 🧠 Key Point

The number of times an operation **actually executes** is not always the same as the number of times the program **checks the condition**.

Here, `print()` may execute only `n` times, but the `if` condition is checked `n²` times.

## ✅ Final Answer

**Time Complexity: `O(n²)`**
