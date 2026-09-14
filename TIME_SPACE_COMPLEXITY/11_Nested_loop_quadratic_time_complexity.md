## 📝 Question

Find the **Time Complexity** of the following code:

```python
n = 10

for i in range(n):
    for j in range(n):
        print(i, j)
```

---

## Explaination

### Step 1 — Analyze the outer loop

The outer loop is:

```python
for i in range(n):
```

It runs `n` times.

For example, if:

```text
n = 3
```

The values of `i` are:

```text
0 → 1 → 2
```

Therefore, the outer loop runs **3 times**.

---

### Step 2 — Analyze the inner loop

Inside the outer loop, we have:

```python
for j in range(n):
```

This also runs `n` times.

The important thing to understand is:

> The inner loop runs completely for **every single iteration** of the outer loop.

---

### Step 3 — Count the total operations

Suppose:

```text
n = 3
```

The execution looks like:

```text
i = 0
    j = 0
    j = 1
    j = 2

i = 1
    j = 0
    j = 1
    j = 2

i = 2
    j = 0
    j = 1
    j = 2
```

The outer loop runs:

```text
3 times
```

For each outer-loop iteration, the inner loop runs:

```text
3 times
```

Therefore:

```text
3 × 3 = 9
```

The `print()` statement executes **9 times**.

---

### Step 4 — Generalize for `n`

The outer loop executes:

```text
n times
```

The inner loop executes:

```text
n times
```

Since the inner loop is inside the outer loop, we **multiply** their complexities:

```text
n × n
```

Therefore:

```text
n²
```

---

### Step 5 — Convert to Big O

The total number of operations is proportional to `n²`.

Therefore:

```text
Time Complexity = O(n²)
```

This is called **Quadratic Time Complexity**.

---

## 🧠 Important Rule

When loops are nested inside each other, their complexities are generally multiplied.

For example:

```python
for i in range(n):
    for j in range(n):
        ...
```

becomes:

```text
O(n) × O(n)

= O(n²)
```

But when loops are consecutive:

```python
for i in range(n):
    ...

for j in range(n):
    ...
```

we add them:

```text
O(n) + O(n)

= O(2n)

= O(n)
```

So remember:

```text
Consecutive loops → Add
Nested loops      → Multiply
```

---

## 📊 Example With Different Values

|    `n` | Operations (`n²`) |
| -----: | ----------------: |
|     10 |               100 |
|    100 |            10,000 |
|  1,000 |         1,000,000 |
| 10,000 |       100,000,000 |

This shows why `O(n²)` algorithms become much slower as the input size increases.

---

## ✅ Final Answer

**Time Complexity: `O(n²)`**

**Reason:** The outer loop runs `n` times, and for each outer-loop iteration, the inner loop also runs `n` times. Therefore, the total number of operations is `n × n = n²`.
