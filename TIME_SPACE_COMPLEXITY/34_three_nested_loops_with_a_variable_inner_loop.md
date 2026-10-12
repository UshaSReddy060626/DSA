## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(n):
        for k in range(j):
            print(i, j, k)
```

## ✅ Answer

**O(n³)**

## Explanation

This question is slightly tricky because the innermost loop depends on `j`.

### Step 1 — Outer loop

```python
for i in range(n):
```

Runs `n` times.

### Step 2 — Middle loop

```python
for j in range(n):
```

For every value of `i`, the middle loop also runs `n` times.

The first two loops therefore account for `n × n = n²` combinations.

### Step 3 — Inner loop

```python
for k in range(j):
```

This loop runs `j` times.

For each outer-loop iteration, the total number of inner-loop executions across all `j` values is:

```text
0 + 1 + 2 + ... + (n - 1)
```

That sum is approximately `n² / 2`.

### Step 4 — Calculate the total

The outer loop runs `n` times, and the work inside it is approximately `n² / 2`.

Therefore:

```text
n × (n² / 2) = n³ / 2
```

Ignoring constants:

```text
O(n³ / 2) = O(n³)
```

## 💡 Key Idea

The middle and inner loops together perform **O(n²)** work for each outer-loop iteration.

Multiplying by the `n` outer iterations gives **O(n³)**.

**Final Answer: O(n³)**