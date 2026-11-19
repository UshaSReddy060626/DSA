## Question

Find the time and auxiliary space complexity.

```python
def process(arr):
    stack = []

    for x in arr:
        while stack and stack[-1] < x:
            stack.pop()

        stack.append(x)

    return stack
```

## Answer

- **Time Complexity:** \(O(n)\) amortized
- **Auxiliary Space Complexity:** \(O(n)\)

Here, \(n\) is the number of elements in the input array.

## Detailed Explanation

**Step 1: Analyze the outer loop**

The outer loop visits every element exactly once.

Therefore, it executes \(n\) times.

**Step 2: Analyze the inner while loop**

At first glance, the nested while loop might suggest \(O(n^2)\).

However, every element is:

- Pushed onto the stack exactly once.
- Popped from the stack at most once.

An element cannot be popped repeatedly after it has been removed.

**Step 3: Count total stack operations**

- Total pushes: \(n\).
- Maximum total pops: \(n\).

Therefore, total stack operations are at most:

\[
n+n=2n
\]

Hence:

\[
\boxed{O(n)}
\]

**Step 4: Calculate auxiliary space**

In the worst case, the stack stores all \(n\) elements.

For example, an array in decreasing order causes no elements to be removed.

Therefore:

\[
\boxed{O(n)}
\]

## Key Takeaway

A nested while loop does not always mean \(O(n^2)\). When each element can be pushed and popped only a constant number of times, the total complexity can be linear.