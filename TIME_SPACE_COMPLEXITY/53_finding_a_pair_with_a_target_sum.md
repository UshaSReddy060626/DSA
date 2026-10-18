## Question

Find the best-case and worst-case time complexities of this code.

```python
def contains_pair(arr, target):
    n = len(arr)

    for i in range(n):
        for j in range(i + 1, n):
            if arr[i] + arr[j] == target:
                return True

    return False
```

## Answer

- **Best case:** \(O(1)\)
- **Worst case:** \(O(n^2)\)

## Explanation

**Step 1: Understand the code**

The function checks whether any two different elements in the list add up to `target`.

For example:

```python
arr = [2, 7, 11, 15]
target = 9
```

The first pair is `2 + 7 = 9`, so the function immediately returns `True`.

**Step 2: Understand the nested loops**

The outer loop selects an element. The inner loop checks the elements that come after it.

In the worst case, the function checks approximately:

\[
\frac{n(n-1)}{2}
\]

pairs.

This grows proportionally to \(n^2\), so the worst-case complexity is:

\[
\boxed{O(n^2)}
\]

**Step 3: Understand the early return**

If the first pair matches the target, the function returns immediately without checking the remaining pairs.

That requires constant work, giving a best-case complexity of:

\[
\boxed{O(1)}
\]

If no pair matches, the function checks all possible pairs, resulting in \(O(n^2)\) time.

## Key Takeaway

When analyzing code with `return` or `break`, consider how much work happens before the function stops.

- Immediate match: \(O(1)\) best case.
- No matching pair: \(O(n^2)\) worst case.

