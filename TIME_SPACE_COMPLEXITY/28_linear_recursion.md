## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    fun(n - 1)
```

## ✅ Answer

**O(n)**

## Explanation

This is a simple recursive function.

The function calls itself with:

```python
n - 1
```

Let's say:

```text
n = 5
```

The calls will look like:

```text
fun(5)
  ↓
fun(4)
  ↓
fun(3)
  ↓
fun(2)
  ↓
fun(1)
```

When `n` becomes `1`, the function stops.

So there are approximately `n` function calls.

Therefore:

```text
n calls × O(1) work per call
```

Gives:

```text
O(n)
```

### 💡 Why is it called Linear Recursion?

Because the input decreases by **1** each time:

```text
n → n-1 → n-2 → n-3 → ...
```

The number of calls grows linearly with `n`.

### 🧠 Remember

```python
fun(n - 1)
```

Usually gives:

**O(n)**

Whereas:

```python
fun(n // 2)
```

usually gives:

**O(log n)**

**Final Answer: O(n)**
