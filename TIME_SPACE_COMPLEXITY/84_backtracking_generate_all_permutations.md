## Question

Given an array containing \(n\) distinct elements, generate all possible permutations using backtracking.

Find the time and auxiliary space complexity.

Example:

```python
arr = [1, 2, 3]
```

Number of permutations = \(3! = 6\).

**Answer:**

- Time Complexity: \(O(n \times n!)\)
- Auxiliary Space Complexity: \(O(n)\), excluding the output.

## Explanation

A permutation is a possible arrangement of all elements.

For example, `[1, 2, 3]` has six arrangements.

**Step 1: Choose the first element**

There are \(n\) choices for the first position.

**Step 2: Choose the second element**

After choosing the first element, only \(n-1\) elements remain.

**Step 3: Continue choosing**

The number of choices keeps decreasing:

\[
n \times (n-1) \times (n-2)\times \cdots \times 1
\]

This gives:

\[
n!
\]

Therefore, the algorithm generates \(n!\) permutations.

**Step 4: Calculate time complexity**

Each permutation takes \(O(n)\) time to construct or output.

Since there are \(n!\) permutations:

\[
T(n)=O(n\times n!)
\]

**Step 5: Calculate space complexity**

The recursion depth is at most \(n\), and the current permutation requires \(O(n)\) space.

Therefore, auxiliary space is:

\[
S(n)=O(n)
\]

This excludes the memory required to store all generated permutations, which is \(O(n\times n!)\).

### Key Takeaway

Generating all permutations becomes expensive as the input grows.

- Number of permutations: \(n!\)
- Time: \(O(n\times n!)\)
- Auxiliary space: \(O(n)\), excluding output.