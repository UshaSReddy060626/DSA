## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(n):
        k = 1

        while k < n:
            print(i, j, k)
            k = k * 2
```

## ✅ Answer

**O(n² log n)**

## Explanation

There are **three loops**.

### Step 1 — First loop

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

### Step 2 — Second loop

```python
for j in range(n):
```

For every `i`, this also runs:

```text
n times
```

So the first two nested loops give:

```text
n × n = n²
```

Therefore:

```text
O(n²)
```

### Step 3 — Third loop

```python
while k < n:
    k = k * 2
```

`k` doubles:

```text
1 → 2 → 4 → 8 → ...
```

So this loop runs:

```text
O(log n)
```

### Step 4 — Multiply Everything

Because all three loops are nested:

```text
O(n) × O(n) × O(log n)
```

Therefore:

```text
O(n² log n)
```

## 💡 Key Idea

For nested loops, multiply their complexities.

```text
n × n × log n
```

becomes:

```text
O(n² log n)
```

### 🧠 Pattern

```text
for n
    for n
        while ×2
```

→ **O(n² log n)**

**Final Answer: O(n² log n)**
