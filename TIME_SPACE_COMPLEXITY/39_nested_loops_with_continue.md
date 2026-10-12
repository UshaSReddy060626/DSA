## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    for j in range(n):
        if j % 2 == 0:
            continue
        print(i, j)
```

## ✅ Answer

**O(n²)**

## Explanation

### Step 1 — Outer loop

The outer loop runs `n` times.

### Step 2 — Inner loop

The inner loop also runs `n` times for each outer iteration.

Therefore, the total number of condition checks is:

\[
n \times n = n^2
\]

### Step 3 — What does `continue` do?

```python
if j % 2 == 0:
    continue
```

`continue` skips the remaining statements in the current iteration and moves to the next iteration.

It does **not** terminate the loop.

The `if` condition is still checked for every value of `j`.

Although `print()` executes only for approximately half the values, the inner loop still performs `n` iterations.

Therefore:

\[
O(n \times n)=O(n^2)
\]

## 💡 Key Idea

- `break` terminates the current loop.
- `continue` skips the rest of the current iteration.
- Neither automatically determines the overall Big O complexity.

**Final Answer: O(n²)**