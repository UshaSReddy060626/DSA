## Question

Find the time and auxiliary space complexity of the following algorithm.

The algorithm finds combinations of positive candidate numbers that add up to a target. Each candidate can be selected multiple times.

```python
def combination_sum(candidates, target):
    result = []
    path = []

    candidates.sort()

    def backtrack(start, remaining):
        if remaining == 0:
            result.append(path.copy())
            return

        for i in range(start, len(candidates)):
            value = candidates[i]

            if value > remaining:
                break

            path.append(value)
            backtrack(i, remaining - value)
            path.pop()

    backtrack(0, target)

    return result
```

Let:
- \(n\) = number of candidates
- \(T\) = target value
- All candidates be distinct positive integers.

## Answer

There is no single simple polynomial bound for this backtracking algorithm.

A useful worst-case upper bound is:

- **Time Complexity:** \(O(n^{T+1})\), for positive integer candidates with minimum value at least 1.
- **Auxiliary Space Complexity:** \(O(T)\), excluding the returned combinations.

The actual running time can be much smaller because of pruning.

## Explanation

### Step 1: Sorting the candidates

```python
candidates.sort()
```

Sorting \(n\) elements takes:

\[
O(n\log n)
\]

### Step 2: Understand the recursion

```python
backtrack(i, remaining - value)
```

The function selects a candidate and calls itself with a smaller remaining target.

Because every candidate is positive, the remaining target decreases by at least 1.

Therefore, the maximum recursion depth is at most \(T\).

### Step 3: Understand the loop

```python
for i in range(start, len(candidates)):
```

At each recursion level, the algorithm may examine up to \(n\) candidates.

The recursion can have up to \(T\) selection levels.

A loose upper bound on the number of explored nodes is:

\[
1+n+n^2+\cdots+n^T
\]

For \(n>1\), this geometric sum is:

\[
O(n^T)
\]

### Step 4: Include the cost of copying results

```python
result.append(path.copy())
```

Copying a combination can take up to \(O(T)\) time.

Using the loose bound on explored nodes, a safe overall upper bound is:

\[
\boxed{O(n^{T+1})}
\]

This includes sorting and copying the combinations.

### Step 5: Understand pruning

```python
if value > remaining:
    break
```

Since the candidates are sorted, once a candidate is larger than the remaining target, all later candidates will also be too large.

The algorithm stops checking those candidates.

This is called pruning.

Pruning avoids exploring branches that cannot produce a valid combination. However, it does not change the loose worst-case upper bound.

### Step 6: Calculate space

The algorithm stores:
- Recursion stack: at most \(O(T)\).
- Current combination (`path`): at most \(O(T)\).
- Sorted candidate list: \(O(n)\) if counting its storage.

The recursion and current path together use:

\[
O(T)
\]

The returned combinations are output space and are excluded from auxiliary space.

If sorting storage is counted, include its implementation-dependent sorting workspace; the overall bound is \(O(n+T)\).

## Key Takeaway

Backtracking complexity depends on how many possible choices are explored.

- Sorting: \(O(n\log n)\).
- Recursion depth: at most \(O(T)\).
- Each level can examine up to \(n\) candidates.
- Pruning reduces unnecessary exploration but does not guarantee polynomial time.
- Auxiliary recursion and path space: \(O(T)\), excluding output.