## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    x = i + 10
    y = i * 2
    z = x + y
    print(z)
```

---

## Explanation

### Step 1 — Count the loop iterations

The loop:

```python
for i in range(n):
```

runs `n` times.

Therefore:

```text
O(n)
```

### Step 2 — Analyze the operations inside

Inside the loop, we have:

```python
x = i + 10
y = i * 2
z = x + y
print(z)
```

Each operation takes approximately **constant time**.

For example:

```text
i + 10     → O(1)
i * 2      → O(1)
x + y      → O(1)
print(z)   → O(1)
```

There are only a fixed number of operations.

Therefore, the work inside the loop is:

```text
O(1)
```

### Step 3 — Combine

The loop runs `n` times, and each iteration performs constant work:

```text
n × O(1)
```

Therefore:

```text
O(n)
```

## 🧠 Important Point

Having several statements inside a loop does **not automatically make the complexity `O(n²)`**.

For example:

```text
4 operations × n iterations = 4n
```

Since `4` is a constant:

```text
O(4n) = O(n)
```

## ✅ Final Answer

**Time Complexity: `O(n)`**
