## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    fun(n - 1)
    fun(n - 1)
```

## ✅ Answer

**O(2ⁿ)**

## Explanation

This function makes **two recursive calls** every time:

```python
fun(n - 1)
fun(n - 1)
```

Let's visualize the calls.

For:

```text
n = 3
```

we get:

```text
              fun(3)
             /      \
        fun(2)      fun(2)
        /   \       /   \
   fun(1) fun(1) fun(1) fun(1)
```

Every function call creates **two more calls**.

The number of calls grows very quickly:

```text
n = 1  →  1
n = 2  →  3
n = 3  →  7
n = 4  →  15
n = 5  →  31
```

This growth is approximately:

```text
2ⁿ
```

Therefore:

```text
Time Complexity = O(2ⁿ)
```

## 💡 Key Idea

A recursive function that branches into **two recursive calls**, with each call reducing `n` by 1, commonly produces exponential complexity.

```python
fun(n - 1)
fun(n - 1)
```

→ **O(2ⁿ)**

### ⚠️ Important

Exponential complexity becomes extremely expensive as `n` increases.

For example:

```text
2¹⁰  = 1,024
2²⁰  = 1,048,576
2³⁰  = 1,073,741,824
```

**Final Answer: O(2ⁿ)**
