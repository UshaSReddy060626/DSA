## Question

Find the time complexity of this algorithm.

It searches for the smallest capacity that can ship all packages within `days` days.

```python
def can_ship(weights, capacity, days):
    required_days = 1
    current_load = 0

    for weight in weights:
        if current_load + weight > capacity:
            required_days += 1
            current_load = 0

        current_load += weight

    return required_days <= days


def ship_within_days(weights, days):
    left = max(weights)
    right = sum(weights)

    answer = right

    while left <= right:
        mid = (left + right) // 2

        if can_ship(weights, mid, days):
            answer = mid
            right = mid - 1
        else:
            left = mid + 1

    return answer
```

Let:
- `n` = number of packages.
- `S` = sum of all package weights.

## Answer

**Time Complexity: \(O(n\log S)\)**

## Explanation

### Step 1: Understand the search range

The minimum possible capacity is the heaviest package:

\[
left=\max(weights)
\]

The maximum possible capacity is the sum of all weights:

\[
right=S
\]

### Step 2: Analyze the binary search

The `while` loop repeatedly divides the capacity search range in half.

Therefore, the number of iterations is:

\[
O(\log S)
\]

### Step 3: Analyze the checking function

```python
for weight in weights:
```

For every possible capacity, the function checks all `n` packages.

Therefore:

\[
O(n)
\]

### Step 4: Combine the complexities

The checking function is called during each binary-search iteration.

\[
T(n)=O(n)\times O(\log S)
\]

\[
\boxed{O(n\log S)}
\]

## Key Takeaway

Binary search is not limited to searching for an element in a sorted array.

It can also search for an optimal answer when:
- A range of possible answers exists.
- You can efficiently check whether a particular answer is feasible.
- Feasibility changes monotonically as the answer changes.

This technique is called **binary search on the answer**.