## Question

Find the time complexity of the following Python code.

```python
i = 0

while i < n:
    print(i)
    i += 3
```

## Answer

**Time Complexity: \(O(n)\)**

## Explanation

### Step 1: Understand the loop

The variable `i` starts at `0`. After each iteration, it increases by `3`.

The values printed are:

```text
0, 3, 6, 9, 12, ...
```

### Step 2: Count the iterations

The loop does not run `n` times exactly. It runs approximately \(n/3\) times.

For example, if `n = 12`, the values are `0`, `3`, `6`, and `9`, giving four iterations.

Therefore:

\[
T(n)\approx \frac{n}{3}
\]

### Step 3: Simplify the complexity

In Big O notation, constant factors are ignored.

\[
O\left(\frac{n}{3}\right)=\boxed{O(n)}
\]

## Key Takeaway

When a loop increments or decrements its variable by a fixed constant, such as `2`, `3`, or `5`, its time complexity is generally \(O(n)\).

**Remember:** Increasing by a fixed number is different from multiplying or dividing by a constant factor. Multiplication or division often leads to logarithmic complexity.