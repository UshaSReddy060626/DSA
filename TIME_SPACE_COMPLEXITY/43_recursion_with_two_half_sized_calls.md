## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    fun(n // 2)
    fun(n // 2)

    for i in range(n):
        print(i)
```

## ✅ Answer

**O(n log n)**

## Explanation

This function contains two recursive calls and one loop.

### Step 1 — Identify the recursive calls

```python
fun(n // 2)
fun(n // 2)
```

Both calls receive approximately half the original input.

The recursion tree has about \(\log_2 n\) levels because the input is repeatedly halved.

### Step 2 — Analyze the loop

```python
for i in range(n):
    print(i)
```

At a call with input `n`, this loop runs `n` times.

So the work done at the current level is \(O(n)\).

### Step 3 — Count work across the recursion tree

At the first level, the loop performs approximately:

\[
n
\]

At the next level, there are two calls, each with input approximately \(n/2\):

\[
2\cdot\frac n2=n
\]

At the following level, there are four calls, each with input approximately \(n/4\):

\[
4\cdot\frac n4=n
\]

Thus, each level performs approximately \(n\) total work.

There are approximately \(\log_2 n\) levels.

Therefore:

\[
T(n)=O(n\log n)
\]

## 💡 Key Idea

Two recursive calls do not automatically mean exponential time.

Here, each call receives half the input, and the total work per level is linear.

**Final Answer: O(n log n)**