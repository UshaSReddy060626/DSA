## 📝 Question

Find the Time Complexity:

```python
n = 8

for i in range(1, n):
    j = 1

    while j < i:
        print(i, j)
        j *= 2
```

## ✅ Answer

**O(n log n)**

## Explanation

### Step 1 — Understand the outer loop

```python
for i in range(1, n):
```

The outer loop runs approximately `n` times.

### Step 2 — Understand the inner loop

```python
j = 1

while j < i:
    j *= 2
```

The value of `j` doubles each time:

```text
1 → 2 → 4 → 8 → ...
```

For a particular value of `i`, the inner loop runs approximately `log₂(i)` times.

For example:

- `i = 2` → about 1 iteration
- `i = 4` → about 2 iterations
- `i = 8` → about 3 iterations

### Step 3 — Calculate the total

The inner loop does not always run `n` times. Its work increases logarithmically as `i` increases.

The total work is approximately:

```text
log 1 + log 2 + log 3 + ... + log n
```

Since each term is at most `log n`, the total is at most:

```text
n log n
```

The overall growth is therefore **O(n log n)**.

## 💡 Key Idea

When the inner loop depends on the outer variable and doubles its own variable, don't automatically classify it as O(n²).

**Final Answer: O(n log n)**