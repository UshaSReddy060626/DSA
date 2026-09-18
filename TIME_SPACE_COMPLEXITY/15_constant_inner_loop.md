## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    for j in range(5):
        print(i, j)
```

---

## Explanation

At first glance, there are two loops, so you might think:

```text
O(n²)
```

But we need to look carefully at the inner loop.

### Step 1 — Analyze the outer loop

```python
for i in range(n):
```

The outer loop runs:

```text
n times
```

Therefore:

```text
O(n)
```

### Step 2 — Analyze the inner loop

The inner loop is:

```python
for j in range(5):
```

Notice that it uses the fixed number `5`, not `n`.

Therefore, it always executes exactly **5 times**, regardless of the input size.

Its complexity is:

```text
O(5)
```

Since `5` is a constant:

```text
O(5) = O(1)
```

### Step 3 — Combine them

The inner loop runs 5 times for every iteration of the outer loop.

Therefore:

```text
n × 5
```

```text
= 5n
```

Ignoring the constant `5`:

```text
= O(n)
```

## 🧠 Important Point

**Not every nested loop is `O(n²)`.**

You must check whether **both loops depend on `n`**.

Compare:

```python
for i in range(n):
    for j in range(n):
```

This is:

```text
O(n²)
```

But:

```python
for i in range(n):
    for j in range(5):
```

is:

```text
O(n)
```

because the inner loop runs a constant number of times.

## ✅ Final Answer

**Time Complexity: `O(n)`**

**Reason:** The outer loop runs `n` times, while the inner loop always runs only 5 times. Therefore, the total operations are `5n`, which simplifies to `O(n)`.
