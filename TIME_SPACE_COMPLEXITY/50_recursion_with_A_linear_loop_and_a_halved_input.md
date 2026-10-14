## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    for i in range(n):
        print(i)

    fun(n // 2)
```

## ✅ Answer

**O(n)**

## Explanation

This function contains a loop and a recursive call.

### Step 1 — Analyze the loop

```python
for i in range(n):
```

The loop runs `n` times.

The work in the first call is **O(n)**.

### Step 2 — Analyze the recursion

```python
fun(n // 2)
```

Each recursive call receives approximately half the previous input.

For example, if `n = 16`, the inputs are:

```text
16 → 8 → 4 → 2 → 1
```

The number of recursive calls is logarithmic, approximately O(log n).

### Step 3 — Calculate the total work

The loop performs the following amount of work across the recursive calls:

```text
n + n/2 + n/4 + n/8 + ...
```

This is a geometric series.

Its sum is less than:

\[
n+\frac n2+\frac n4+\cdots=2n
\]

Ignoring the constant factor:

\[
O(2n)=O(n)
\]

Therefore:

\[
\boxed{O(n)}
\]

## 💡 Key Idea

The number of recursive calls alone does not determine the time complexity.

You must calculate the total work performed across all calls.

Here, the input halves each time, and the loop gets proportionally smaller. The total work remains linear.

**Final Answer: O(n)**