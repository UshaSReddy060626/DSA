## Question

Find the overall time complexity of the following Python code.

```python
arr = []

for i in range(n):
    arr.append(i)
```

## Answer

**Overall Time Complexity: \(O(n)\) amortized**

## Explanation

**Step 1: Understand `append()`**

The `append()` method adds one element to the end of a list.

```python
arr = []
arr.append(10)
arr.append(20)

print(arr)  # [10, 20]
```

A single append usually takes \(O(1)\) time.

**Step 2: Count the iterations**

The loop runs `n` times.

Each iteration appends exactly one element.

Therefore, there are `n` append operations.

**Step 3: Calculate the total work**

\[
T(n)=n \times O(1)
\]

\[
\boxed{O(n)}
\]

### What does amortized mean?

Python sometimes needs to allocate a larger block of memory when the list becomes full. That occasional resizing can take \(O(n)\) time.

However, most append operations are constant-time, and the cost averaged across a long sequence of appends is \(O(1)\) per operation.

Therefore, `n` append operations take \(O(n)\) total time.

## Key Takeaway

Do not automatically assume that every operation inside a loop makes the complexity \(O(n^2)\).

- `n` appends: \(O(n)\) total.
- One append: \(O(1)\) amortized.
- Repeatedly copying increasingly large lists: potentially \(O(n^2)\).