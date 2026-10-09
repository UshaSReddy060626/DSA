## 📝 Question

Find the Time Complexity:

```python
i = 1

while i < n:
    for j in range(n):
        print(i, j)

    i = i * 2
```

## ✅ Answer

**O(n log n)**

## Explanation

Let's analyze the two loops.

### Step 1 — Outer loop

```python
i = 1

while i < n:
    ...
    i = i * 2
```

The value of `i` doubles:

```text
1 → 2 → 4 → 8 → 16 → ...
```

Therefore, the outer loop runs:

```text
O(log n)
```

times.

### Step 2 — Inner loop

```python
for j in range(n):
```

This runs:

```text
n times
```

So:

```text
O(n)
```

### Step 3 — Multiply

The inner loop runs every time the outer loop runs.

Therefore:

```text
O(log n) × O(n)
```

Which gives:

```text
O(n log n)
```

## 💡 Key Idea

The **order of the loops doesn't matter** when they are nested.

For example:

```text
n × log n
```

and

```text
log n × n
```

both give:

```text
O(n log n)
```

### 🧠 Pattern

```python
while i < n:
    i = i * 2
```

→ **O(log n)**

Inside it:

```python
for j in range(n):
```

→ **O(n)**

Together:

**O(n log n)**

**Final Answer: O(n log n)**
