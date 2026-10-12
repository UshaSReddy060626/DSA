## 📝 Question

Find the Time Complexity:

```python
def fun(n):
    if n <= 1:
        return

    fun(n - 1)
    fun(n // 2)
```

## ✅ Answer

**O(2ⁿ)** as a safe asymptotic upper bound; more precisely, the tight growth is also exponential, with a rate smaller than \(2^n\).

## Explanation

This function makes two recursive calls:

```python
fun(n - 1)
fun(n // 2)
```

The first call reduces the input by one. The second divides it by two.

A simple way to understand the growth is to count the calls made by the first branch alone.

### Step 1 — Follow the first branch

```text
fun(n)
  ↓
fun(n - 1)
  ↓
fun(n - 2)
  ↓
fun(n - 3)
  ↓
...
```

This branch alone produces approximately `n` calls.

### Step 2 — Include the second branch

Every non-base call also invokes `fun(n // 2)`, which creates additional calls.

So the total is greater than linear, but we must analyze both branches together to determine the tight bound.

The recurrence is approximately:

\[
T(n)=T(n-1)+T(\lfloor n/2\rfloor)+O(1)
\]

A tight bound for this recurrence is:

\[
T(n)=2^{\Theta((\log n)^2)}
\]

This grows faster than every polynomial in `n`, but slower than \(2^{cn}\) for any fixed positive constant \(c\).

## 💡 Key Idea

When a recursive function makes calls with **different input sizes**, don't simply count the number of calls and guess the answer.

Write the recurrence first, then analyze how the subproblems shrink.

**Final Answer: \(2^{\Theta((\log n)^2)}\)**