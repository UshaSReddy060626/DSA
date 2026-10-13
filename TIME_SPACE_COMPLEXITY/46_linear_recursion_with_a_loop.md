## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    for i in range(n):
        print(i)

    fun(n - 1)
```

## ✅ Answer

**O(n²)**

## Explanation

This function contains a loop and a recursive call.

### Step 1 — Analyze the loop

```python
for i in range(n):
```

For an input of `n`, the loop runs `n` times.

Its cost is **O(n)**.

### Step 2 — Analyze the recursion

```python
fun(n - 1)
```

The function calls itself with an input smaller by 1.

The recursive inputs are:

```text
n, n-1, n-2, n-3, ..., 2, 1
```

### Step 3 — Add the work at every level

The loop performs:

- `n` operations in the first call
- `n - 1` operations in the second call
- `n - 2` operations in the third call
- And so on

The total work is:

\[
n+(n-1)+(n-2)+\cdots+1
\]

Using the sum formula:

\[
\frac{n(n+1)}{2}
\]

Expanding:

\[
\frac{n^2+n}{2}
\]

The dominant term is \(n^2\). Big O ignores constants and lower-order terms.

Therefore:

\[
\boxed{O(n^2)}
\]

### 💡 Key Idea

A recursive function with `n` calls is not necessarily O(n).

You must also count the work performed **inside each call**.

- O(1) work per call × n calls → O(n)
- O(n) work per call across shrinking inputs → O(n²) in this example

**Final Answer: O(n²)**