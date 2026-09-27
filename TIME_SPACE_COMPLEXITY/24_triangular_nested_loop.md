## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(i, n):
        print(i, j)
```

## ✅ Answer

**O(n²)**

## Explanation

The outer loop runs `n` times.

But the inner loop does not always run `n` times.

* When `i = 0` → inner loop runs `n` times
* When `i = 1` → inner loop runs `n - 1` times
* When `i = 2` → inner loop runs `n - 2` times
* ...
* When `i = n - 1` → inner loop runs `1` time

So the total number of operations is:

```text
n + (n-1) + (n-2) + ... + 2 + 1
```

This is:

```text
n(n + 1) / 2
```

Ignoring constants:

```text
n(n + 1) / 2
≈ n²
```

Therefore:

```text
Time Complexity = O(n²)
```

## 💡 Key Idea

Even though the inner loop gets smaller for every iteration, the total work still grows proportionally to **n²**.

### Pattern to remember

```python
for i in range(n):
    for j in range(i, n):
```

Usually → **O(n²)**
