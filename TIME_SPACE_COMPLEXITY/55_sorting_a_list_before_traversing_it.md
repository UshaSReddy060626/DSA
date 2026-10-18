## Question

Find the overall time complexity of this code.

```python
def process(arr):
    arr.sort()

    for x in arr:
        print(x)
```

Assume `arr` contains `n` elements.

## Answer

**Time Complexity: \(O(n\log n)\)** in the average/general case.

## Explanation

**Step 1: Analyze the sorting operation**

```python
arr.sort()
```

Python's built-in list sort uses Timsort.

- Typical and worst-case sorting time: \(O(n\log n)\).
- Best-case sorting time for already ordered data: \(O(n)\).

**Step 2: Analyze the loop**

```python
for x in arr:
    print(x)
```

The loop visits all `n` elements.

Therefore, its time complexity is \(O(n)\), assuming each print operation is treated as constant-time.

**Step 3: Add the complexities**

For the general case:

\[
T(n)=O(n\log n)+O(n)
\]

The \(n\log n\) term grows faster than \(n\), so it dominates.

\[
\boxed{O(n\log n)}
\]

## Key Takeaway

When operations run one after another, add their time complexities and keep the dominant term.

For this code, sorting dominates the traversal. If the input is already sorted, Python's sort can run in \(O(n)\), making the overall time \(O(n)\) for that best-case input.