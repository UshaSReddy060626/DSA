## Question

Find the time complexity of the following Python code.

```python
arr = list(range(n))

for i in range(n):
    temp = arr[:i]
```

## Answer

**Time Complexity: \(O(n^2)\)**

## Explanation

**Step 1: Understand list slicing**

The expression `arr[:i]` creates a new list containing the first `i` elements

For example:

```python
arr = [10, 20, 30, 40]

print(arr[:1])  # [10]
print(arr[:2])  # [10, 20]
print(arr[:3])  # [10, 20, 30]
```

Copying `i` elements takes \(O(i)\) time.

**Step 2: Calculate the work in each iteration**

- When `i = 0`, the slice takes \(O(1)\) time.
- When `i = 1`, it takes \(O(1)\) time.
- When `i = 2`, it takes \(O(2)\) time.
- When `i = 3`, it takes \(O(3)\) time.
- This continues until `i = n - 1`.

**Step 3: Add the total work**

\[
T(n)=0+1+2+\cdots+(n-1)
\]

Using the sum formula:

\[
T(n)=\frac{n(n-1)}{2}
\]

Ignoring constants and lower-order terms:

\[
\boxed{O(n^2)}
\]

## Key Takeaway

List slicing is not always \(O(1)\). Creating a slice of \(k\) elements takes \(O(k)\) time. When slicing happens repeatedly inside a loop, the total complexity can become \(O(n^2)\).