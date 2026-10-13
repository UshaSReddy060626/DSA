## 📝 Question

Find the Time Complexity:

```python
for i in range(n):
    j = 1

    while j < n:
        for k in range(j):
            print(i, j, k)
        j *= 2
```

## ✅ Answer

**O(n²)**

## Explanation

### Step 1 — Outer loop

```python
for i in range(n):
```

Runs `n` times.

Complexity: **O(n)**.

### Step 2 — Middle loop

```python
j = 1
while j < n:
    j *= 2
```

The values of `j` are:

```text
1 → 2 → 4 → 8 → 16 → ...
```

The middle loop runs **O(log n)** times.

### Step 3 — Inner loop

```python
for k in range(j):
```

Unlike a constant-size loop, this loop runs `j` times.

Across the middle loop, the total work is approximately:

\[
1+2+4+8+\cdots+n
\]

This geometric series sums to less than \(2n\).

Therefore, the combined middle and inner loops perform **O(n)** work per outer iteration.

### Step 4 — Calculate the total

The outer loop runs `n` times:

\[
O(n)\times O(n)=O(n^2)
\]

## 💡 Key Idea

A logarithmic loop containing a loop whose length doubles each time does not necessarily produce O(n log n).

The inner work forms a geometric series, so the combined work is O(n).

**Final Answer: O(n²)**