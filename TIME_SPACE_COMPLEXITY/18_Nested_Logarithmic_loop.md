## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 16

i = 1

while i < n:
    j = 1

    while j < n:
        j = j * 2

    i = i * 2
```

---

## Explanation

This question contains **two nested logarithmic loops**.

---

### Step 1 — Analyze the outer loop

The outer variable is:

```python
i = i * 2
```

So:

```text
1 → 2 → 4 → 8 → 16
```

The outer loop runs approximately:

```text
log n
```

times.

Therefore:

```text
O(log n)
```

---

### Step 2 — Analyze the inner loop

Inside every outer-loop iteration, `j` starts again at `1`:

```python
j = 1
```

Then:

```python
j = j * 2
```

So it also follows:

```text
1 → 2 → 4 → 8 → 16
```

Therefore, the inner loop runs:

```text
O(log n)
```

times.

---

### Step 3 — Multiply because the loops are nested

The inner loop runs completely for every iteration of the outer loop.

Therefore:

```text
O(log n) × O(log n)
```

Which gives:

```text
O((log n)²)
```

or:

```text
O(log² n)
```

## 🧠 Key Rule

Just like:

```text
O(n) × O(n) = O(n²)
```

we can have:

```text
O(log n) × O(log n) = O(log² n)
```

## ✅ Final Answer

**Time Complexity: `O((log n)²)`**
