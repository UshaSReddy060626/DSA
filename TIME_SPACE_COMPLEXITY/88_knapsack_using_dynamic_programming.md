## Question

Given \(n\) items, each having a weight and value, find the maximum total value that can fit inside a knapsack of capacity \(W\).

Each item can either be selected once or not selected.

Determine the time and space complexity using Dynamic Programming.

**Answer:**

- Time Complexity: \(O(nW)\)
- Space Complexity: \(O(nW)\) for the standard 2D DP approach.

### Explanation

The 0/1 Knapsack problem is an optimization problem where we choose items to maximize their total value without exceeding the weight capacity.

**Step 1: Understand the inputs**

Suppose we have:

| Item | Weight | Value |
|---|---:|---:|
| A | 2 | 10 |
| B | 3 | 20 |
| C | 4 | 30 |

Knapsack capacity:

\[
W=5
\]

We must select items whose total weight does not exceed 5.

**Step 2: Create a DP table**

Create a table with:

- \(n+1\) rows representing items.
- \(W+1\) columns representing capacities.

Each cell stores the maximum value possible using the available items and capacity.

**Step 3: Fill the table**

For each item and each capacity, decide:

- Do not select the item.
- Select the item if its weight fits.

Choose the option that gives the maximum value.

**Step 4: Calculate time complexity**

There are approximately \(n\times W\) cells.

Each cell requires constant-time work.

Therefore:

\[
T(n,W)=O(nW)
\]

**Step 5: Calculate space complexity**

The DP table contains approximately \(n\times W\) entries.

Therefore:

\[
S(n,W)=O(nW)
\]

*Note:* A space-optimized 1D DP implementation can reduce auxiliary space to \(O(W)\).

### Key Takeaway

Dynamic Programming avoids repeatedly solving the same subproblems.

- Time: \(O(nW)\)
- Standard 2D auxiliary space: \(O(nW)\)
- Optimized auxiliary space: \(O(W)\)