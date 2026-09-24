## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    for j in range(i):
        print(i, j)
```

---

## Explanation

This is a nested loop, but the inner loop does **not** always run `n` times.

The inner loop depends on `i`.

### Step 1 — See how many times the inner loop runs

Suppose:

```text
n = 5
```

Then:

```text
i = 0 → inner loop runs 0 times
i = 1 → inner loop runs 1 time
i = 2 → inner loop runs 2 times
i = 3 → inner loop runs 3 times
i = 4 → inner loop runs 4 times
```

So the total number of executions is:

```text
0 + 1 + 2 + 3 + 4
```

This is the sum:

```text
n(n - 1) / 2
```

### Step 2 — Simplify

The expression is:

```text
n(n - 1) / 2
```

Expanding:

```text
(n² - n) / 2
```

Ignoring constants and lower-order terms:

```text
O(n²)
```

## 🧠 Important Point

Even though the inner loop doesn't run `n` times for every `i`, the total number of operations still grows quadratically.

This pattern is called a **triangular loop**.

## ✅ Final Answer

**Time Complexity: `O(n²)`**
