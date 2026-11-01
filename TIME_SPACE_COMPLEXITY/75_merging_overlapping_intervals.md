## Question

Find the time and space complexities of this algorithm.

```python
def merge_intervals(intervals):
    intervals.sort()

    merged = []

    for start, end in intervals:
        if not merged or merged[-1][1] < start:
            merged.append([start, end])
        else:
            merged[-1][1] = max(
                merged[-1][1], end
            )

    return merged
```

Let `n` be the number of intervals.

## Answer

- **Time Complexity:** \(O(n\log n)\)
- **Auxiliary Space:** \(O(n)\) for the merged output, excluding the sorting implementation's internal workspace.

## Explanation

### Step 1: Analyze sorting

```python
intervals.sort()
```

The algorithm sorts all `n` intervals.

Sorting takes:

\[
O(n\log n)
\]

### Step 2: Analyze the loop

```python
for start, end in intervals:
```

The loop visits every interval exactly once.

Inside the loop, it performs constant-time comparisons and updates.

Therefore:

\[
O(n)
\]

### Step 3: Combine the operations

\[
T(n)=O(n\log n)+O(n)
\]

The sorting operation dominates.

\[
\boxed{O(n\log n)}
\]

### Step 4: Calculate space complexity

In the worst case, none of the intervals overlap.

The `merged` list then stores all `n` intervals.

Therefore, its output space is:

\[
\boxed{O(n)}
\]

## Key Takeaway

Many interval problems follow this pattern:

1. Sort the intervals.
2. Traverse them once.
3. Merge overlapping intervals.

Sorting usually dominates the time complexity, making the overall complexity \(O(n\log n)\).