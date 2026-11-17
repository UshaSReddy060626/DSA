## Question

Given \(n\) people and \(n\) tasks, find the minimum cost of assigning exactly one task to each person using Bitmask Dynamic Programming.

Determine the time and space complexity.

**Answer:**

- Time Complexity: \(O(n2^n)\)
- Space Complexity: \(O(2^n)\)

### Explanation

Bitmask DP represents a group of selected tasks using binary bits.

**Step 1: Understand bitmask**

Suppose there are 3 tasks.

A bitmask can represent which tasks have already been assigned.

For example:

```python
mask = 101
```

This means tasks 1 and 3 are assigned, while task 2 is not.

**Step 2: Create DP states**

Define:

\[
dp[mask]
\]

as the minimum assignment cost for the tasks represented by `mask`.

The number of possible masks is:

\[
2^n
\]

**Step 3: Try assigning an unassigned task**

For each state, try every task whose corresponding bit is not set.

Update the next state with the minimum possible cost.

**Step 4: Calculate time complexity**

There are \(2^n\) possible masks.

For each mask, we may check up to \(n\) tasks.

Therefore:

\[
T(n)=n\times 2^n
\]

\[
\boxed{O(n2^n)}
\]

**Step 5: Calculate space complexity**

The DP array stores one value for every possible mask.

Therefore:

\[
\boxed{O(2^n)}
\]

### Key Takeaway

Bitmask DP uses binary representations to track combinations of selected elements.

- Time: \(O(n2^n)\)
- Space: \(O(2^n)\)
- Useful for assignment problems and Traveling Salesperson Problem.