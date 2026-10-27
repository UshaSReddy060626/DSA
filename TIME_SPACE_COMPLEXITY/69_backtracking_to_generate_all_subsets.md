## Question

Find the time complexity of this recursive function.

```python
def generate_subsets(arr, index=0, current=None):
    if current is None:
        current = []

    if index == len(arr):
        print(current)
        return

    generate_subsets(arr, index + 1, current)

    current.append(arr[index])
    generate_subsets(arr, index + 1, current)
    current.pop()
```

Assume `arr` contains `n` elements. For this analysis, count the cost of printing a subset of size `k` as \(O(k)\).

## Answer

- **Time Complexity:** \(O(n2^n)\), including printing all subsets.
- **Auxiliary Space:** \(O(n)\), excluding the output and recursion-call overhead beyond the recursion depth.

## Explanation

### Step 1: Understand the two choices

For every element, the function makes two choices:

1. Exclude the element from the current subset.
2. Include the element in the current subset.

For example, for `[A, B]`, the possible subsets are:

```text
[]
[A]
[B]
[A, B]
```

### Step 2: Count the subsets

Every element has two possibilities: included or excluded.

Therefore, the number of subsets is:

\[
2^n
\]

The recursive function reaches one leaf for each subset.

### Step 3: Account for printing

Printing each subset costs time proportional to its size. Across all subsets, each of the `n` elements appears in exactly half of the subsets.

The total number of element appearances is:

\[
n2^{n-1}
\]

Thus, printing all subsets requires \(O(n2^n)\) total time. This dominates the recursive traversal's \(O(2^n)\) work.

\[
\boxed{O(n2^n)}
\]

### Step 4: Calculate auxiliary space

The `current` list can hold up to `n` elements, and the recursion depth is at most `n`.

Therefore, the auxiliary space is:

\[
\boxed{O(n)}
\]

This excludes storing or printing the complete output.

## Key Takeaway

Backtracking can explore exponentially many possibilities.

When generating all subsets, there are \(2^n\) possible subsets. If each subset takes up to \(O(n)\) time to output, the total time is \(O(n2^n)\).

The distinction between traversal cost and output cost is important in interview questions.