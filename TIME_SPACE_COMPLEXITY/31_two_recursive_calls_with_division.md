## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    fun(n // 2)
    fun(n // 2)
```

## ✅ Answer

**O(n)**

## Explanation

At first glance, this may look like **O(2ⁿ)** because there are two recursive calls.

But we must also consider that `n` is divided by 2.

The function creates this pattern:

```text
fun(n)
      /       \
 fun(n/2)   fun(n/2)
    / \       / \
fun(n/4) ... ...
```

Let's see the number of calls at each level.

### Level 0

```text
1 call
```

### Level 1

```text
2 calls
```

### Level 2

```text
4 calls
```

### Level 3

```text
8 calls
```

The number of levels is:

```text
log n
```

At the same time, the number of calls doubles at each level.

The total number of calls is approximately:

```text
1 + 2 + 4 + 8 + ... + n
```

This geometric series sums to approximately:

```text
2n
```

Ignoring the constant:

```text
O(2n) = O(n)
```

Therefore:

```text
Time Complexity = O(n)
```

## 💡 Important Lesson

Don't simply see **two recursive calls** and immediately say `O(2ⁿ)`.

You must also check how the input changes.

### Compare

```python
fun(n - 1)
fun(n - 1)
```

→ **O(2ⁿ)**

But:

```python
fun(n // 2)
fun(n // 2)
```

→ **O(n)**

The division by 2 dramatically reduces the recursion depth.

**Final Answer: O(n)**
