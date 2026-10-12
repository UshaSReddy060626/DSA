## 📝 Question

Find the Time Complexity:

```python
i = n

while i > 0:
    print(i)
    i -= 3
```

## ✅ Answer

**O(n)**

## Explanation

### Step 1 — Understand the update

```python
i -= 3
```

This subtracts 3 from `i` after each iteration.

For example, if `n = 12`, the values are:

```text
12 → 9 → 6 → 3
```

The loop stops when `i` becomes zero or negative.

### Step 2 — Count the iterations

The variable decreases by a fixed amount of 3.

So the approximate number of iterations is:

```text
n / 3
```

### Step 3 — Apply Big O rules

The time complexity is:

```text
O(n / 3)
```

Big O ignores constant factors:

```text
O(n / 3) = O(n)
```

Therefore, the time complexity is **O(n)**.

## 💡 Key Idea

Compare these two loops:

**Loop A — Subtracting a constant**

```python
i = n
while i > 0:
    i -= 3
```

Complexity: **O(n)**

**Loop B — Dividing by a constant**

```python
i = n
while i > 0:
    i //= 2
```

Complexity: **O(log n)**

Subtracting a fixed amount takes linear time; repeatedly dividing by a fixed factor takes logarithmic time.

**Final Answer: O(n)**