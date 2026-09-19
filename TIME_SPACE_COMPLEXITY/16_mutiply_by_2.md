## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10
i = 1

while i < n:
    print(i)
    i = i * 2
```

---

## Explanation

### Step 1 — Observe how `i` changes

The value of `i` starts at `1`.

Every iteration multiplies it by `2`.

For example, if:

```text
n = 16
```

The values are:

```text
1 → 2 → 4 → 8 → 16
```

The loop stops when `i` reaches `n`.

### Step 2 — Look at the growth

The value is growing exponentially:

```text
1
2
4
8
16
32
64
...
```

We are asking:

> How many times do we need to multiply `1` by `2` to reach `n`?

The answer is approximately:

```text
log₂(n)
```

### Step 3 — Find Big O

Therefore:

```text
Time Complexity = O(log n)
```

## 🧠 Important Point

Both of these patterns have logarithmic complexity:

```python
n = n // 2
```

and:

```python
i = i * 2
```

So remember:

```text
Divide by 2 → O(log n)
Multiply by 2 → O(log n)
```

## ✅ Final Answer

**Time Complexity: `O(log n)`**
