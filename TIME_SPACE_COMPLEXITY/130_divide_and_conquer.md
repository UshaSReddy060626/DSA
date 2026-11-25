## Question

Find the time and auxiliary space complexity of the following recursive algorithm.

```python
def solve(n):
    if n <= 1:
        return 1

    a = solve(n // 2)
    b = solve(n // 4)

    total = 0

    for i in range(n):
        total += i

    return a + b + total
```

Determine:
1. The time complexity.
2. The auxiliary space complexity.

## Answer

- **Time Complexity:** \(O(n)\)
- **Auxiliary Space Complexity:** \(O(\log n)\)

## Explanation

### Step 1: Identify the recursive calls

```python
a = solve(n // 2)
b = solve(n // 4)
```

The function makes two recursive calls:

- First call processes \(n/2\).
- Second call processes \(n/4\).

### Step 2: Calculate the work outside recursion

```python
for i in range(n):
    total += i
```

This loop runs \(n\) times.

Each iteration performs constant work.

Therefore:

\[
O(n)
\]

### Step 3: Form the recurrence relation

The recurrence is:

\[
T(n)=T(n/2)+T(n/4)+O(n)
\]

We need to account for both recursive calls and the loop.

### Step 4: Understand the recursive work

At the first level, the work is:

\[
n
\]

At the next level, the total input sizes are:

\[
\frac n2+\frac n4=\frac{3n}{4}
\]

At the following level:

\[
\frac{3n}{4}\times\frac{3}{4}
=\frac{9n}{16}
\]

The work decreases geometrically:

\[
n+\frac{3n}{4}+\frac{9n}{16}+\cdots
\]

This is a geometric series with common ratio \(3/4\).

Its total is bounded by:

\[
n\left(1+\frac34+\frac{9}{16}+\cdots\right)
\]

\[
\leq \frac{n}{1-\frac34}
\]

\[
=4n
\]

Therefore:

\[
\boxed{T(n)=O(n)}
\]

### Step 5: Calculate auxiliary space

The maximum recursion depth is determined by the longest recursive path.

The longest path repeatedly divides \(n\) by 2:

\[
n\rightarrow\frac n2\rightarrow\frac n4
\rightarrow\frac n8\rightarrow\cdots
\]

The number of divisions required to reach 1 is:

\[
\log_2 n
\]

Therefore, the recursion stack requires:

\[
\boxed{O(\log n)}
\]

## Key Takeaway

When a recursive function makes calls on different fractions of the input:

1. Write the recurrence correctly.
2. Calculate the work done outside recursion.
3. Examine the total input size at each recursion level.
4. Use the longest recursive path to calculate stack space.

For this problem:

\[
T(n)=T(n/2)+T(n/4)+O(n)
\]

- Time: \(O(n)\)
- Auxiliary space: \(O(\log n)\)