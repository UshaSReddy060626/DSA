## Question

Find the time and space complexity.

```python
def calculate(n):
    for i in range(n):
        j = n

        while j > i:
            j -= 1
```

## Answer

- **Time Complexity:** \(O(n^2)\)
- **Space Complexity:** \(O(1)\)

## Explanation

1. The outer loop executes \(n\) times.
2. When `i = 0`, the inner loop runs approximately \(n\) times.
3. When `i = 1`, it runs approximately \(n-1\) times.
4. When `i = 2`, it runs approximately \(n-2\) times.
5. Total iterations are:

   \[
   n+(n-1)+(n-2)+\cdots+1
   \]

6. Using the sum formula:

   \[
   \frac{n(n+1)}{2}=O(n^2)
   \]

7. Only variables `i` and `j` are used, so auxiliary space is constant.

## Key Takeaway

Nested loops do not always execute \(n \times n\) times exactly. Calculate the total iterations when the inner loop depends on the outer variable.