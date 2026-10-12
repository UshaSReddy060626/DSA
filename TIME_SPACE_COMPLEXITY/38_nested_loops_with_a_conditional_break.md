## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    j = 0

    while j < n:
        if j == i:
            break
        j += 1
```

## ✅ Answer

**O(n²)**

## Explanation

### Step 1 — Outer loop

```python
for i in range(n):
```

The outer loop runs `n` times.

### Step 2 — Inner loop

```python
j = 0
while j < n:
```

The inner loop starts at zero for every outer-loop iteration.

But it stops when `j == i`.

Let's examine a few values:

| `i` | Inner-loop iterations |
|---:|---:|
| 0 | 1 |
| 1 | 2 |
| 2 | 3 |
| 3 | 4 |
| ... | ... |
| n − 1 | n |

### Step 3 — Calculate the total

The total number of iterations is:

\[
1+2+3+\cdots+n=\frac{n(n+1)}{2}
\]

Ignoring constants and lower-order terms:

\[
O(n^2)
\]

## 💡 Key Idea

A `break` can reduce the number of iterations, but it does not necessarily make a nested loop linear.

Here, the inner loop's workload grows with `i`, producing a quadratic total.

**Final Answer: O(n²)**