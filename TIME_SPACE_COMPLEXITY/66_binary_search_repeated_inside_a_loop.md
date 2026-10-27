## Question

Find the time complexity of the following code.

```python
def process(arr, targets):
    for target in targets:
        left = 0
        right = len(arr) - 1

        while left <= right:
            mid = (left + right) // 2

            if arr[mid] == target:
                break
            elif arr[mid] < target:
                left = mid + 1
            else:
                right = mid - 1
```

Assume `arr` is sorted, `arr` contains `n` elements, and `targets` contains `m` elements.

## Answer

**Time Complexity: \(O(m\log n)\)** in the worst case.

## Explanation

### Step 1: Analyze the outer loop

```python
for target in targets:
```

The loop processes every target, so it runs `m` times.

### Step 2: Analyze the inner loop

The `while` loop performs binary search on `arr`.

Each iteration approximately halves the remaining search space, so one search takes \(O(\log n)\) time in the worst case.

### Step 3: Combine the complexities

The binary search runs once for every target.

\[
T(n,m)=m\times O(\log n)
\]

Therefore:

\[
\boxed{O(m\log n)}
\]

## Key Takeaway

When an algorithm runs inside another loop, multiply their costs.

- One binary search: \(O(\log n)\)
- `m` binary searches: \(O(m\log n)\)

Always identify which input variable controls each loop.