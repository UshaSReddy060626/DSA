## Question

Given an \(n \times n\) chessboard, place \(n\) queens so that no two queens attack each other.

Determine the worst-case time and auxiliary space complexity using backtracking.

**Answer:**

- Worst-case Time Complexity: \(O(n!)\) using row-by-row placement with column and diagonal checks in \(O(1)\).
- Auxiliary Space Complexity: \(O(n)\), excluding the output board.

### Explanation

The N-Queens problem places queens on a chessboard such that no two queens share:

- The same row.
- The same column.
- The same diagonal.

**Step 1: Place the first queen**

Start from the first row and choose a valid column for the queen.

There are \(n\) possible columns initially.

**Step 2: Move to the next row**

Try placing another queen in a column where it cannot attack the previously placed queens.

**Step 3: Use backtracking**

If no valid position is available:

- Remove the previously placed queen.
- Try another column.
- Continue searching for a valid arrangement.

**Step 4: Calculate time complexity**

Because only one queen is placed in each row and column, the maximum number of possible placements can be bounded by:

\[
n\times(n-1)\times(n-2)\times\cdots\times1
\]

Therefore, the worst-case search bound is:

\[
\boxed{O(n!)}
\]

This assumes constant-time column and diagonal checks using suitable tracking arrays or sets.

**Step 5: Calculate space complexity**

The algorithm uses:

- A recursion stack of depth \(n\).
- Arrays or sets to track occupied columns and diagonals.

Each requires \(O(n)\) space.

Therefore:

\[
\boxed{O(n)}
\]

This excludes the output board, which requires \(O(n^2)\) space if stored.

### Key Takeaway

N-Queens uses backtracking to explore possible queen placements and reject invalid arrangements.

- Worst-case time bound: \(O(n!)\)
- Auxiliary space: \(O(n)\)
- Output board storage: \(O(n^2)\)