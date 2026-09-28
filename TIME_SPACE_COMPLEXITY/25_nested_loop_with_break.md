## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(n):
        if j == n - 1:
            break
        print(i, j)
```

## ✅ Answer

**O(n²)**

## Explanation

At first, the `break` might make this look faster.

Let's examine it carefully.

The outer loop runs:

```text
n times
```

For every outer-loop iteration, the inner loop starts from `0`.

The inner loop stops when:

```python
j == n - 1
```

So it still runs approximately:

```text
n - 1
```

times.

Therefore:

```text
Outer loop = n
Inner loop ≈ n
```

Total:

```text
n × (n - 1)
```

Expanding:

```text
n² - n
```

Big O ignores the lower-order term:

```text
O(n² - n) = O(n²)
```

Therefore:

```text
Time Complexity = O(n²)
```

## 💡 Important Lesson

A `break` does **not automatically mean O(1)**.

You must ask:

> **How many times does the loop actually execute?**

Here, the `break` happens near the **end** of the inner loop, so the inner loop still performs almost `n` operations for every outer iteration.

### Remember

```python
for i in range(n):
    for j in range(n):
        if condition:
            break
```

The complexity depends on **where the break happens**.

If the break happens immediately → it may reduce the complexity.

If the break happens near the end → it may still be **O(n²)**.
