## 📝 Question

Find the Time Complexity in terms of `n`:

```python
for i in range(n):
    for j in range(100):
        for k in range(n):
            print(i, j, k)
```

## ✅ Answer

**O(n²)**

## Explanation

This question tests whether you can distinguish a constant loop from a variable loop.

### Step 1 — First loop

```python
for i in range(n):
```

Runs `n` times.

Complexity: **O(n)**

### Step 2 — Second loop

```python
for j in range(100):
```

Runs exactly 100 times.

Because 100 is fixed, its complexity is **O(1)**.

### Step 3 — Third loop

```python
for k in range(n):
```

Runs `n` times.

Complexity: **O(n)**

### Step 4 — Multiply the complexities

The loops are nested:

```text
O(n) × O(1) × O(n)
```

Therefore:

```text
O(n²)
```

The total number of executions is approximately:

```text
n × 100 × n = 100n²
```

Ignoring the constant 100 gives **O(n²)**.

## 💡 Key Idea

The number of nested loops alone does not determine the complexity.

Look at the range of each loop:

- `range(n)` → O(n)
- `range(100)` → O(1)
- `range(n)` → O(n)

**Final Answer: O(n²)**