## Question

Find the overall time complexity of this function.

```python
def process_values(arr):
    stack = []

    for x in arr:
        while stack and stack[-1] < x:
            stack.pop()

        stack.append(x)

    return stack
```

Assume `arr` contains `n` elements.

## Answer

**Overall Time Complexity: \(O(n)\) amortized**

## Explanation

### Step 1: Analyze the outer loop

```python
for x in arr:
```

The outer loop processes every element exactly once.

It runs `n` times.

### Step 2: Why isn't the nested `while` loop automatically \(O(n^2)\)?

At first glance, the nested loops might suggest \(O(n^2)\).

However, the `while` loop removes elements from the stack. Once an element is removed, it cannot be removed again.

### Step 3: Count pushes and pops

- Every element is pushed onto the stack once.
- Every element can be popped at most once.

Across the entire function, there are at most `n` pushes and `n` pops.

Thus, the total number of stack operations is at most proportional to \(2n\).

\[
T(n)=O(n)+O(n)=O(n)
\]

Therefore:

\[
\boxed{O(n)}
\]

### Step 4: Calculate space complexity

In the worst case, the stack stores all `n` elements.

\[
\boxed{O(n)\text{ auxiliary space}}
\]

## Key Takeaway

Nested loops do not always mean \(O(n^2)\).

When the inner loop removes or permanently processes elements, count how many times each element can participate in that operation.

This is an example of **amortized analysis**, a useful technique for monotonic stacks and several array problems.