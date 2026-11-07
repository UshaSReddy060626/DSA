## Question

Given:
- A text of length \(n\).
- A pattern of length \(m\).

Determine the time and space complexity of the Knuth-Morris-Pratt (KMP) algorithm for finding the pattern in the text.

**Answer:**

- LPS array construction: \(O(m)\)
- Pattern searching: \(O(n)\)
- Total time complexity: \(O(n+m)\)
- Auxiliary space complexity: \(O(m)\)

## Explanation

KMP is a string-matching algorithm that finds a pattern inside a larger text without repeatedly checking the same characters.

**Step 1: Build the LPS array**

LPS means *Longest Proper Prefix which is also a Suffix*.

It helps the algorithm decide how far to shift the pattern when a mismatch occurs.

Building the LPS array requires processing the pattern once.

Therefore:

\[
O(m)
\]

**Step 2: Search the pattern**

The algorithm compares the pattern with the text.

When characters match, it moves forward.

When a mismatch occurs, it uses the LPS array to avoid unnecessary comparisons.

The text index never moves backward, so the searching process takes:

\[
O(n)
\]

**Step 3: Calculate total time**

Add both operations:

\[
T(n,m)=O(m)+O(n)
\]

Therefore:

\[
\boxed{O(n+m)}
\]

**Step 4: Calculate space**

The LPS array stores information for each character of the pattern.

Therefore, auxiliary space is:

\[
\boxed{O(m)}
\]

### Key Takeaway

KMP avoids unnecessary repeated comparisons while searching for a pattern.

- LPS construction: \(O(m)\)
- Searching: \(O(n)\)
- Total time: \(O(n+m)\)
- Auxiliary space: \(O(m)\)