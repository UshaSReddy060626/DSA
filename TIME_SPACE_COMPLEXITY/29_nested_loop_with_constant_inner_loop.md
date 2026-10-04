## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(10):
        print(i, j)
```

## ✅ Answer

**O(n)**

## Explanation

Let's look at the two loops separately.

### Outer loop

```python
for i in range(n):
```

Runs:

```text
n times
```

So:

```text
O(n)
```

### Inner loop

```python
for j in range(10):
```

Always runs exactly **10 times**.

10 is a constant.

Therefore:

```text
O(10) = O(1)
```

### Total Complexity

The loops are nested, so we multiply:

```text
O(n) × O(1)
```

Therefore:

```text
O(n)
```

The actual number of executions is:

```text
10n
```

But Big O ignores constants:

```text
O(10n) = O(n)
```

### 💡 Key Idea

A nested loop does **not always mean O(n²)**.

If the inner loop runs a fixed number of times, it is constant.

**Final Answer: O(n)**
